# Operations Intructions

## Setup Account

```
export GITLAB_ACCESS_TOKEN=<YOUR-ACCESS-TOKEN>
export TF_STATE_NAME=dev-accountsetup
tofu init \
    -backend-config="address=https://gitlab.com/api/v4/projects/39368785/terraform/state/$TF_STATE_NAME" \
    -backend-config="lock_address=https://gitlab.com/api/v4/projects/39368785/terraform/state/$TF_STATE_NAME/lock" \
    -backend-config="unlock_address=https://gitlab.com/api/v4/projects/39368785/terraform/state/$TF_STATE_NAME/lock" \
    -backend-config="username=diegopuertas" \
    -backend-config="password=$GITLAB_ACCESS_TOKEN" \
    -backend-config="lock_method=POST" \
    -backend-config="unlock_method=DELETE" \
    -backend-config="retry_wait_min=5"
```
