## Awesome tools
* Dynamoose is a modeling tool for Amazon's DynamoDB (inspired by Mongoose) - https://github.com/dynamoose/dynamoose
* Find how much bandwidth "Up to" actually means - https://ec2throughput.info/
* https://github.com/darkbitio/aws-recon - A multi-threaded AWS security-focused inventory collection tool
* aws diagrams with python: https://diagrams.mingrammer.com/docs/getting-started/examples
* open source tool by aws for "building intuitive, engaging, and inclusive user experiences at scale" https://cloudscape.design/
* [ai use cases explorer](https://aiexplorer.aws.amazon.com/)
* instances (ec2, rds, opensearch, elasticcache) pricing comparison - https://instances.vantage.sh/

## Awesome AWS Projects and Code
* small utils, scripts, projects: https://github.com/awsbot-labs?tab=repositories
* Print lambda event, context: https://gist.github.com/gene1wood/24e431859c7590c8c834
* Custom resource helper: https://github.com/aws-cloudformation/custom-resource-helper
* Feature flags for AWS: https://awslabs.github.io/aws-lambda-powertools-python/latest/utilities/feature_flags/
* mock aws services - https://github.com/spulec/moto

## Awesome AWS Services
* Dynamodb blog: https://blog.yugabyte.com/11-things-you-wish-you-knew-before-starting-with-dynamodb
* CloudFormation ref cheat sheet: https://theburningmonk.com/cloudformation-ref-and-getatt-cheatsheet/
* AWS IP Ranges: https://ip-ranges.amazonaws.com/ip-ranges.json
* EventBridge Pipes - connect services - https://dev.to/aws-builders/about-amazon-eventbridge-pipes-32ln
* ec2 instant connect (without a public ip): https://github.com/aidansteele/rdsconn, https://aws.amazon.com/blogs/compute/secure-connectivity-from-public-to-private-introducing-ec2-instance-connect-endpoint-june-13-2023/

## Awesome Serverless
* https://serverlessland.com/
* Lambda Power Tools: https://awslabs.github.io/aws-lambda-powertools-python/, [Validator](https://awslabs.github.io/aws-lambda-powertools-python/utilities/parser/), [github](https://github.com/awslabs/aws-lambda-powertools-python)
* https://github.com/epsagon/lambda-memory-performance-benchmark
* Warming lambdas
  * https://www.npmjs.com/package/lambda-warmer
  * https://pypi.org/project/lambda-warmer-py/
* https://github.com/alexcasalboni/aws-lambda-power-tuning 
* https://lumigo.io/aws-lambda-performance-optimization/
* Get least priviledged IAM policy by lambda code: https://github.com/puresec/serverless-puresec-cli
* https://aws.amazon.com/blogs/compute/announcing-improved-vpc-networking-for-aws-lambda-functions/
* AWS services mock lib - https://github.com/spulec/moto
* Python Lambda multithreading [blog](https://medium.com/tech-carnot/understanding-multiprocessing-in-aws-lambda-with-python-6f50c11d57e4), [aws blog](https://aws.amazon.com/blogs/compute/parallel-processing-in-python-with-aws-lambda/)
* [understanding-aws-lambda-scaling-and-throughput](https://aws.amazon.com/blogs/compute/understanding-aws-lambda-scaling-and-throughput/)
* [Lambda code signing best practices](https://aws.amazon.com/blogs/security/best-practices-and-advanced-patterns-for-lambda-code-signing/)
* cold start etc.
  * instead of using static provisioned concurrency, you can do it dynamically using Application auto scaling feature: "target tracking policy" and cloudwatch alarms
    * define the lambda as a "scalable target"
    * scaling policy - rules that aws uses to manage scaling, we'll use target tracking
    * we can use "ProvisionedConcurrencyUtilization" (% of what's used from the prov. concurrency) - 0..1
    * BUT we will use a custom metric because that the pre-defined metric, the alarm will use average values TODO - complete
    * https://docs.aws.amazon.com/autoscaling/application/userguide/application-auto-scaling-target-tracking.html


  * Lambda warmer, custom metric:
    * https://github.com/robhowley/lambda-warmer-py
    * https://lumigo.io/blog/monitor-lambda-cold-start-durations-with-cloudwatch/
    * https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:374852340823:applications~async-custom-metrics

## Awesome AWS Security
* saml2aws - get temp creds for machine: https://github.com/Versent/saml2aws
* Policy Sentry: https://dashbird.io/knowledge-base/aws-lambda/resource-allocation-and-performance/
* Cloud Custodian: https://cloudcustodian.io/docs/quickstart/index.html
* cfn-nag: https://github.com/stelligent/cfn_nag
* checkkov - like cfn-nag but also Terraform, K8S, serverless, ARM Templates, etc. including a link to remediation
* cf-guard: https://github.com/aws-cloudformation/cloudformation-guard
* cloudmapper - https://github.com/duo-labs/cloudmapper

## Awesome AWS Blogs
* https://aws.amazon.com/blogs/compute/introducing-the-new-aws-step-functions-workflows-collection/
* Private Link for Lambda: https://aws.amazon.com/blogs/aws/new-use-aws-privatelink-to-access-aws-lambda-over-private-aws-network/
* Feature toggles with lambda power tools: https://isenberg-ran.medium.com/aws-lambda-feature-toggles-made-simple-580b0c444233
* https://rhinosecuritylabs.com/aws/s3-ransomware-part-2-prevention-and-defense/
* Allowing Lambda from another account to invoke a Lambda: https://aws.amazon.com/premiumsupport/knowledge-center/lambda-function-assume-iam-role/
* https://aws-blog.de/2021/01/cross-account-resource-access-invalid-principal-in-policy.html
* SQS Fifo - [Does Ordered and Exactly Once Messaging Really Exist](https://sookocheff.com/post/messaging/dissecting-sqs-fifo-queues/#:~:text=Exactly-Once%20%E2%80%94%20Nothing%20in%20Life,and%20not%20delivered%20to%20consumer
* custom resource helper (non cdk): https://aws.amazon.com/blogs/infrastructure-and-automation/aws-cloudformation-custom-resource-creation-with-python-aws-lambda-and-crhelper/

## Awesome AWS Videos
* S3 security - https://www.youtube.com/watch?v=xFzJw6wJ8eY
* Architect your serverless apps for hyperscaling: https://www.youtube.com/watch?v=GNUSdekIaMw, https://virtual.reinvent.awsevents.com/session-virtual/?v2477da705118cc74fd14460db021e1784e2eed5a7982c6482ec95cb2e86d259644b8741959f52a49e0e6908b82a9d860=68123CE134D220C29FD48B00F58D6FF92E063EB5A78D853133A569A2413C5985A00AEC91498516EB6E9D372E271C58C0

## Awesome re:*
* https://www.infoq.com/news/2020/12/aws-reinvent-2020/

## Which AWS DB?
* [Nice flow diagram](https://github.com/roybenyosef/AwesomeEverything/blob/main/which-aws-db.jpeg) - missing MemoryDB :D
* 

## Other Clouds
* Azure-AWS Service comparison: https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services

## Awesome AWS re:invent (and other) videos:
* Another Day, Another Billion Packets (VPC, EC2): https://www.youtube.com/watch?v=St3SE4LWhKo
* Playlist for important videos: https://www.youtube.com/playlist?list=PL_RVC-cMNyYTz8zlxq117O1bfji-knooI
* Securing ECS: https://www.youtube.com/watch?v=nKhtSmYRfxs

## Awesome AWS Projects
* https://aws.amazon.com/getting-started/hands-on/build-log-analytics-solution/services-costs/
* 

## CICD
* https://scalesec.com/blog/identity-federation-for-github-actions-on-aws/

## Horrible AWS
* IPv6 on AWS whitepaper (I hope I never have to read this): https://d1.awsstatic.com/whitepapers/IPv6-on-AWS.pdf
* https://aws.amazon.com/blogs/infrastructure-and-automation/keep-your-aws-resources-when-you-rename-an-aws-cloudformation-stack/

## Dynamodb
* https://dynobase.dev/dynamodb-locking/
* https://dynobase.dev/dynamodb-transactions/
* https://dynobase.dev/dynamodb-nodejs/#read-transaction
* 


## Tips
* if you have sigv4 then in a ddos - you don't pay for failed sigv4 calls
