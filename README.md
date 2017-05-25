# Node.js demo-app
This is a demo application used in my AgileJKL presentation on 29th March 2017.

## ecs-cli commands

```bash
ECS_CLUSTER_NAME="ecs-demo"
AWS_PROFILE_NAME="gofore-crew"

ecs-cli configure --region eu-west-1 --profile ${AWS_PROFILE_NAME} --cluster ecs-demo
```

```bash
TARGET_GROUP_ARN="arn:aws:elasticloadbalancing:eu-west-1:<account-id>:targetgroup/ecs-demo/32fe582e7e9bd0cb"
ECS_TASK_ROLE="arn:aws:iam::<account-id>:role/agilejklEcs"

ecs-cli compose service up --target-group-arn ${TARGET_GROUP_ARN} --container-name agilejkl-node --container-port 3000 --role ${ECS_TASK_ROLE}
```

```bash
ecs-cli compose service scale 8
```
