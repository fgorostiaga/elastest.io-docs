<div class="range range-xs-left">
<div class="cell-xs-10 cell-lg-6 text-md-left inset-md-right-80 cell-lg-push-1 offset-top-50 offset-lg-top-0">
<h2 id="content" class="h1">Deploying ElasTest</h2>
<div class="offset-top-30 offset-md-top-50">
</div>
</div>
</div>

<h2 class="h3 no-border">Native deployment: Docker</h2>

_(Automatic launching ElasTest on startup)_

<h2 class="h3 no-border">Cloud Formation</h2>

First of all you'll need an AWS account. To achive that, follow those [steps](http://docs.aws.amazon.com/AmazonSimpleDB/latest/DeveloperGuide/AboutAWSAccounts.html).

Then, you can go to [AWS CloudFormation Pane](https://eu-west-1.console.aws.amazon.com/cloudformation/) and create a **new stack**. You will need the **json** included on this repo to complete the task. The form you'll see on the second step have to be filled with the following information:

| Parameter | Value | Details | Ready? |
| --- | --- | --- | --- |
| Stack name | The name of the stack | Elastest is OK | yes |
| ElastestCertificateType | selfsigned or own cert | You can choose which type of certificate use with elastest | no |
| ElastestExecutionMode | normal, experimental-lite or experimental | Choose Elastest' execution mode | yes |
| ElastestPassword | elastest | Password to access the platform | no |
| ElastestUsername | elastest | Username to access the platform | no |
| ElastestVersion | latest | which version of elastest do you want to launch | yes |
| InstanceType | m4.large | Elastest needs resources to run, please be genereous | yes |
| KeyName |  | RSA key to access the instance through SSH | yes |
| LetsEncryptEmail | | Email to recive Let's Encrypt notifications | no |
| OwnCertCRT | Block | The certificate chain | no |
| OwnCertKEY | Block | The private key | no |
| SwapSize | 4 | The amount of swap memory in GB | yes |

When the stack has finished the deployment, you can check *output* tab to see the URL to access your application.