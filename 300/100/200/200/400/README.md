# 400 - Fix hard failures when mirroring

After 14 consecutive unsuccessful retries, the mirroring process is marked as a hard failure and mirroring attempts stop. This failure is visible in either the:

- Project’s main dashboard.
- Pull mirror settings page.

To resume project mirroring, [force an update](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html#force-an-update).

If many projects are affected by this problem, such as after a long network or server outage, you can use the [Rails console](https://docs.gitlab.com/ee/administration/operations/rails_console.html) to identify and update all affected projects with this command:

```
Project.find_each do |p|
  if p.import_state && p.import_state.retry_count >= 14
    puts "Resetting mirroring operation for #{p.full_path}"
    p.import_state.reset_retry_count
    p.import_state.set_next_execution_to_now(prioritized: true)
    p.import_state.save!
  end
end
```
