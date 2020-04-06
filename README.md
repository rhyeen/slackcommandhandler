# Every run

Run the commands in the `_secrets` file in the terminal.

```
serverless deploy
```

# Setup on a new machine

## Setup serverless

```
npm install -g serverless
serverless
```

This will guide you through the process to sign into serverless for deploys.

## Create Secret Files

Any file that has secrets in it has been added to [.gitignore](.gitignore), so they will need to be recreated on your local machine.

### _secrets

Create a new file at root, `_secrets`.  Paste the following into it for creation:

```
export AWS_ACCESS_KEY_ID=XXX
export AWS_SECRET_ACCESS_KEY=XXX
serverless config credentials --provider aws --key XXX --secret XXX
```

Find the AWS IAM user.  You'll need to regenerate these tokens for the user, as AWS only shows them once,
and I didn't store them anywhere to retrieve.  If you are not me, follow the AWS IAM setup instructions at either of the following:

  * https://github.com/serverless/serverless/blob/master/docs/providers/aws/guide/credentials.md
  * https://www.freecodecamp.org/news/make-a-serverless-slack-app/

### serverless.yml

Create a new file at root, `serverless.yml`.  Paste this into it: https://github.com/johnagan/serverless-slack-app/blob/master/serverless.yml

You'll need to fill out its `xxx...` areas, as desribed here: https://github.com/johnagan/serverless-slack-app

Note that you'll want to change `provider.profile` to default, so that it works with the `serverless config credentials` that we use above.