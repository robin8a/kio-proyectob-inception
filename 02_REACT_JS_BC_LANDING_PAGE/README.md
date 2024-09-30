
# References
- [API (GRAPHQL) Relational Databases](https://docs.amplify.aws/cli-legacy/graphql-transformer/relational/)
- [Amplify Getting Started](https://docs.amplify.aws/start)
- [Policy AWS Simulator](https://policysim.aws.amazon.com)
- [Scalar types in AWS AppSync](https://docs.aws.amazon.com/appsync/latest/devguide/scalars.html)
- [GraphQL API Security with AWS AppSync and Amplify](https://aws.amazon.com/blogs/mobile/graphql-security-appsync-amplify/)
- https://tokhun.io/explore/serialized/jVRMXB
- https://docs.ipfs.io/concepts/what-is-ipfs/
- https://www.europapress.es/economia/finanzas-00340/noticia-mito-galeria-arte-nft-hispanohablantes-abre-puertas-20210916183841.html
- https://js.ipfs.io/
- https://enlear.academy/complete-guide-to-aws-amplify-studio-4a14801d85e4


# Starting React App

```sh
source ~/.bash_profile
npx create-react-app kio-blocke-landing-page-rjs-app
cd kio-blocke-landing-page-rjs-app
npm start
```

# Amplify

## Configure

- Just when is a new aws account
```sh
amplify configure
```

## init
```sh
amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project kioblockelandingpage
The following configuration will be applied:

Project information
| Name: kioblockelandingpage
| Environment: dev
| Default editor: Visual Studio Code
| App type: javascript
| Javascript framework: react
| Source Directory Path: src
| Distribution Directory Path: build
| Build Command: npm run-script build
| Start Command: npm run-script start

? Initialize the project with the above configuration? Yes
Using default provider  awscloudformation
? Select the authentication method you want to use: AWS profile

For more information on AWS Profiles, see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html

? Please choose the profile you want to use kio-blocke-rjs-landing-page-profile
Adding backend environment dev to AWS Amplify app: d2knd63ceusx6h

Deployment completed.
Deployed root stack kioblockelandingpage [ ======================================== ] 4/4
        amplify-kioblockelandingpage-… AWS::CloudFormation::Stack     CREATE_COMPLETE                Fri Apr 28 2023 10:53:52…     
        UnauthRole                     AWS::IAM::Role                 CREATE_COMPLETE                Fri Apr 28 2023 10:53:43…     
        DeploymentBucket               AWS::S3::Bucket                CREATE_COMPLETE                Fri Apr 28 2023 10:53:51…     
        AuthRole                       AWS::IAM::Role                 CREATE_COMPLETE                Fri Apr 28 2023 10:53:44…     

✔ Help improve Amplify CLI by sharing non sensitive configurations on failures (y/N) · yes
Deployment state saved successfully.
✔ Initialized provider successfully.
✅ Initialized your environment successfully.

Your project has been successfully initialized and connected to the cloud!

Some next steps:
"amplify status" will show you what you've added already and if it's locally configured or deployed
"amplify add <category>" will allow you to add features like user login or a backend API
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify console" to open the Amplify Console and view your project status
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

Pro tip:
Try "amplify add api" to create a backend API and then "amplify push" to deploy everything```

# Codecommit

[Create repo](https://docs.aws.amazon.com/cli/latest/reference/codecommit/create-repository.html)
```sh
# nano ~/.aws/credentials
# export PATH=~/Library/Python/3.8/bin:$PATH
# export PATH=~/Library/Python/3.7/bin:$PATH
# source ~/.bash_profile
# test
aws s3 ls --profile kio-blocke-rjs-landing-page-profile
export AWS_PROFILE=kio-blocke-rjs-landing-page-profile

# aws codecommit create-repository --repository-name MyDemoRepo --repository-description "My demonstration repository" --tags Team=Saanvi
aws codecommit create-repository --repository-name kio-blocke-landing-page-rjs-app --repository-description "Landing page for blocke" --tags Team=kio --region us-east-1 

```

```json
{
    "repositoryMetadata": {
        "accountId": "389863671664",
        "repositoryId": "7dc87342-8e28-4701-bb34-2d47e6777322",
        "repositoryName": "kio-blocke-landing-page-rjs-app",
        "repositoryDescription": "Landing page for blocke",
        "lastModifiedDate": "2023-04-28T10:58:18.578000-05:00",
        "creationDate": "2023-04-28T10:58:18.578000-05:00",
        "cloneUrlHttp": "https://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-blocke-landing-page-rjs-app",
        "cloneUrlSsh": "ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-blocke-landing-page-rjs-app",
        "Arn": "arn:aws:codecommit:us-east-1:389863671664:kio-blocke-landing-page-rjs-app"
    }
}
```
## git

```sh
ssh-keygen
kio_blocke_landing_page_rjs_app
/Users/robinochoa/.ssh/kio_blocke_landing_page_rjs_app

cat ~/.ssh/kio_blocke_landing_page_rjs_app.pub

```


```sh
cd ~/.ssh
ls
nano config

# Add

# CodeCommit hosts
Host kio_blocke_landing_page_rjs_app
   HostName git-codecommit.us-east-1.amazonaws.com
   User APKAVVRNPQ5YCCOPDG3T
   IdentityFile ~/.ssh/kio_blocke_landing_page_rjs_app

```

<!-- https://xiaolishen.medium.com/use-multiple-ssh-keys-for-different-github-accounts-on-the-same-computer-7d7103ca8693 -->

```sh
git clone ssh://kio_blocke_landing_page_rjs_app/v1/repos/kio-blocke-landing-page-rjs-app


# git remote -v
# git remote rm origin
# git init
# git clone ssh://kio_blocke_landing_page_rjs_app/v1/repos/kio-blocke-landing-page-rjs-app

git remote add origin ssh://kio_blocke_landing_page_rjs_app/v1/repos/kio-blocke-landing-page-rjs-app
git push --set-upstream origin master
git push


git clone ssh://kio_blocke_landing_page_rjs_app/v1/repos/kio-proyectob-rjs-app

```


# Amplify hosting

## Result
```sh
amplify add hosting
│ FrontEnd Env │ Domain                                      │
├──────────────┼─────────────────────────────────────────────┤
│ master       │ https://master.d6r9pw8s9c88j.amplifyapp.com │
```

# Amplify auth

```sh
amplify add auth
Using service: Cognito, provided by: awscloudformation
 
 The current configured provider is Amazon Cognito. 
 
 Do you want to use the default authentication and security configuration? Default configuration
 Warning: you will not be able to edit these selections. 
 How do you want users to be able to sign in? Username
 Do you want to configure advanced settings? No, I am done.
✅ Successfully added auth resource kiosuancultivosacuicf502e377 locally

✅ Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

(node:27903) [DEP0128] DeprecationWarning: Invalid 'main' field in '/Users/robinochoa/.npm-global/lib/node_modules/@aws-amplify/cli/node_modules/cloudform/package.json' of 'packages/cloudform/index.js'. Please either fix that or report it to the module author
(Use `node --trace-deprecation ...` to show where the warning was created)

```


# Amplify api

```sh
amplify add api
? Select from one of the below mentioned services: GraphQL
? Here is the GraphQL API that we will create. Select a setting to edit or continue (Use arrow keys)
  Name: kiosuancultivosacuic 
  Authorization modes: API key (default, expiration time: 7 days from now) 
? Here is the GraphQL API that we will create. Select a setting to edit or continue Authorization modes: API key (default, expiration time: 7 days from now)
? Choose the default authorization type for the API Amazon Cognito User Pool
Use a Cognito user pool configured as a part of this project.
? Configure additional auth types? Yes
? Choose the additional authorization types you want to configure for the API API key
API key configuration
? Enter a description for the API key: api-for-not-authorize
? After how many days from now the API key should expire (1-365): 365
? Here is the GraphQL API that we will create. Select a setting to edit or continue Continue
? Choose a schema template: One-to-many relationship (e.g., “Blogs” with “Posts” and “Comments”)

⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY authorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at /Users/robinochoa/Documents/react_ws/kio-blocke-landing-page-rjs-app/amplify/backend/api/kiosuancultivosacuic/schema.graphql or place .graphql files in a directory at /Users/robinochoa/Documents/react_ws/kio-blocke-landing-page-rjs-app/amplify/backend/api/kiosuancultivosacuic/schema
✔ Do you want to edit the schema now? (Y/n) · yes
Edit the file in your editor: /Users/robinochoa/Documents/react_ws/kio-blocke-landing-page-rjs-app/amplify/backend/api/kiosuancultivosacuic/schema.graphql
✅ Successfully added resource kiosuancultivosacuic locally

✅ Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud
```


# amplify storage
```sh
amplify add storage
? Select from one of the below mentioned services: Content (Images, audio, video, etc.)
(node:33192) [DEP0128] DeprecationWarning: Invalid 'main' field in '/Users/robinochoa/.npm-global/lib/node_modules/@aws-amplify/cli/node_modules/cloudform/package.json' of 'packages/cloudform/index.js'. Please either fix that or report it to the module author
(Use `node --trace-deprecation ...` to show where the warning was created)
✔ Provide a friendly name for your resource that will be used to label this category in the project: · kiosuanacuaboxstorage
✔ Provide bucket name: · kiosuancultivosacuic6b8f0ee9fcbe45a9803254d820f
✔ Who should have access: · Auth and guest users
✔ What kind of access do you want for Authenticated users? · create/update, read, delete
✔ What kind of access do you want for Guest users? · read
✔ Do you want to add a Lambda Trigger for your S3 Bucket? (y/N) · no
⚠️ Auth configuration is required to allow unauthenticated users, but it is not configured properly.
✅ Successfully updated auth resource locally.
✅ Successfully added resource kiosuanacuaboxstorage locally

⚠️ If a user is part of a user pool group, run "amplify update storage" to enable IAM group policies for CRUD operations
✅ Some next steps:
"amplify push" builds all of your local backend resources and provisions them in the cloud
"amplify publish" builds all of your local backend and front-end resources (if you added hosting category) and provisions them in the cloud
```


# Amplify API

```sh
amplify add api
# ? Please select from one of the below mentioned services: GraphQL
# ? Provide API name: kiojupplacesreserver
# ? Choose the default authorization type for the API API key
# ? Enter a description for the API key: 
# ? After how many days from now the API key should expire (1-365): 365
# ? Do you want to configure advanced settings for the GraphQL API No, I am done.
# ? Do you have an annotated GraphQL schema? No
# ? Do you want a guided schema creation? Yes
# ? What best describes your project: One-to-many relationship (e.g., “Blogs” with “Posts” and “Comments”)
# ? Do you want to edit the schema now? Yes
# Please edit the file in your editor: /Users/robinochoa/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema.graphql
# ? Press enter to continue 

# The following types do not have '@auth' enabled. Consider using @auth with @model
#          - Place
#          - Reserve
# Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 


# GraphQL schema compiled successfully.

# Edit your schema at /Users/robinochoa/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema.graphql or place .graphql files in a directory at /Users/robinochoa/Documents/react_ws/kio-jup-places-reserve-rjs-app/amplify/backend/api/kiojupplacesreserver/schema
# Successfully added resource kiojupplacesreserver locally

# Some next steps:
# "amplify push" will build all your local backend resources and provision it in the cloud
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

```

## Result

```sh
amplify push   

```

# AWS enviroment
- https://docs.amplify.aws/cli/teams/overview/
  
# aws amplify storage unauthenticated access
- https://medium.com/floom/public-read-access-for-aws-amplify-storage-9eb5621abff
- https://docs.amplify.aws/lib/storage/configureaccess/q/platform/js/
- https://docs.amplify.aws/lib/storage/configureaccess/q/platform/js/#customization
- https://stackoverflow.com/questions/60936666/getting-missing-required-field-principal-when-adding-policy-to-s3-bucket

> Continuar con 
> http://suanapicardano-env.eba-rjbtbq22.us-east-2.elasticbeanstalk.com/
> https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create-deploy-python-django.html
> Estaba en la instalacion y pruebas de EB y configuracion de las credenciales, ya fue instalado en la instacia
> https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create-deploy-python-django.html


To create an environment and deploy your Django application


# Connect to Serverless Aurora Database using Cloud 9
https://aws.amazon.com/getting-started/hands-on/configure-connect-serverless-mysql-database-aurora/#:~:text=To%20access%20your%20new%20Aurora,will%20login%20to%20your%20cluster.

- Connect psql https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToPostgreSQLInstance.html
- Errors: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToPostgreSQLInstance.html
```sh

# Install on amazon2
sudo amazon-linux-extras install postgresql10

psql \
   --host=<DB instance endpoint> \
   --port=<port> \
   --username=<master username> \
   --password \
   --dbname=<database name> 


   psql --host=mypostgresql.c6c8mwvfdgv0.us-west-2.rds.amazonaws.com --port=5432 --username=awsuser --password --dbname=mypgdb 
```


```sql
CREATE TABLE accounts (
	user_id serial PRIMARY KEY,
	username VARCHAR ( 50 ) UNIQUE NOT NULL,
	password VARCHAR ( 50 ) NOT NULL,
	email VARCHAR ( 255 ) UNIQUE NOT NULL,
	created_on TIMESTAMP NOT NULL,
        last_login TIMESTAMP 
);
```

# RDS and amplify, other options
- [Connect Amplify DataStore with existing SQL datasources; adding offline and sync features in your application](https://aws.amazon.com/blogs/mobile/connect-amplify-datastore-with-existing-sql-datasources-adding-offline-and-sync-features-in-your-application/)
- https://alatech.medium.com/micro-frontends-with-aws-amplify-part-4-3790f4fc1677


# Amplify Auth Observable

- https://dev.to/beavearony/aws-amplify-auth-angular-rxjs-simple-state-management-3jhd
- https://redux-observable.js.org/


1. Cambiar el logo
2. Cambiar al ico
3. Cambiar la frase
4. Habilitar el ADMON admon_acuabox
5. Probar si funciona CRUD de ...


# The Best Libraries for React I18n (Interna)
- https://medium.com/i18n-and-l10n-resources-for-developers/best-libraries-for-react-i18n-5bc37c20bd63