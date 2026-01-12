Create OpenID Connect
---------------
eksctl utils associate-iam-oidc-provider --cluster RoboShop-dev --approve

Create ServiceAccount
---------------------

eksctl create iamserviceaccount --cluster RoboShop-dev --name pass-secret --namespace roboshop --attach-policy-arn arn:aws:iam::287223951807:policy/RoboShopMongoDBSecretReader --approve

Get Secret Value
----------------

aws secretsmanager get-secret-value --secret-id roboshop/dev/mysql_password --query SecretString --output text