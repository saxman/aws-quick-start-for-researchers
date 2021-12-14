# AWS Quick Start Guide for Researchers

## Introduction to the Cloud and AWS

*The Cloud* enables researchers to access IT resources, such as Linux or Windows workstations and servers, databases, storage for files, computing clusters, natural language processing tools, etc., in a matter of minutes, and to pay for those resources only when they’re needed. Additionally, cloud service providers, such as AWS, take on a certain degree of IT administration of cloud services, such as ensuring that a server’s operating system and database have the latest security patches installed. The ease of access, pay-as-you-go pricing, and *shared security model* of the cloud contrasts to traditional research computing, where workstations and servers need to be requested and paid for in advance, can take weeks or months to arrive and be configured, and need to be maintained, and secured, for the lifetime of the resource.

Also, in the context of researcher IT, the cloud promotes *research reproducibility*, as templates for IT resources, such as a high performance computing cluster configured with specific analytical algorithms, can be shared between researchers, enabling the recipient of the template to recreate research environments with minimal effort. Broadly, the cloud enables researchers to focus on their research, and spend less time on managing hardware, operating systems, and the services required to conduct their research.

The main categories of AWS services that researchers are typically interested in are cloud-based workspaces (e.g. a computer to log into to do work on), storage for research data, and the ability to run tools and services that have been shared by collaborators or other researchers (e.g. open source projects). As users of cloud services, researchers also need to be aware of how to monitor their spending, as well as securing their cloud environment. Each of these use cases are discussed at a high level within this guide, in order to help researchers to quickly get started with using AWS.

See also:

* [Research and Technical Computing on AWS](https://aws.amazon.com/government-education/research-and-technical-computing/)
* [Five ways to use AWS for research (starting right now)](https://aws.amazon.com/blogs/publicsector/five-ways-use-aws-research-starting-now/)
* [No-cost online AWS training pathway for researchers and research IT](https://aws.amazon.com/blogs/publicsector/no-cost-online-aws-training-pathway-researchers-research-it/)

## Accessing the AWS Cloud

The AWS (Web) Management Console is the simplest and most common way for researchers configure and interact with AWS services. In order to begin using AWS services, you will need to use the console to create an AWS account, and to provide payment information (e.g. a credit card) that AWS will charge if you enable an AWS service *and* the service usage exceed the free tier limit that is associated with the service. Most AWS services provide a certain amount of usage, without cost, for evaluating the service, which is called the service’s *free tier.* **** Monitoring your free tier usage is covered in the next section.

To create a new AWS account, follow the these steps using your web browser:

1. Open the [Amazon Web Services (AWS) home page](https://aws.amazon.com/).
2. Choose *Create an AWS Account*.

Note: If you signed in to AWS recently, choose Sign in to the Console. If Create a new AWS account isn't visible, first choose Sign in to a different account, and then choose Create a new AWS account.

1. Enter your email address, password, AWS account name, and then choose *Continue*. Be sure that you enter your account information correctly, especially your email address. If you enter your email address incorrectly, you can't access your account.

Once you’ve provide the required information and are logged into the AWS Management Console, you can start exploring the services that are available on AWS, by either selecting the *Services* button on the top-left of the console interface, or by entering a service name in the search box at the top. AWS offers over 200 services, ranging from lower-level workstation and server environments (e.g. Amazon EC2), to higher-level services, such as fully automated natural language processing (Amazon Comprehend). For this guide, we will focus on the primary AWS services that researchers find to be the most useful.

For more information, see:

* [How do I create and activate a new AWS account?](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/)
* [What is the AWS Management Console?](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/learn-whats-new.html)

## Managing expenses

For viewing and managing the costs associated with using AWS services, AWS provides a Billing and Cost Management interface within the AWS Management Console. You can access this interface by searching for “billing” in the console and selecting *Billing* in the results.

Using the *Cost Explorer* feature of this interface, you can view and analyze your AWS costs and usage over time, including historic usage and expense forecasts. After visiting the cost explorer dashboard for the first time, it takes 24 hours for data to become available, and after the dashboard has been initialized, data is refreshed every 24 hours.

AWS automatically provides free tier usage alerts using AWS Budgets to help you track your free tier usage. These alerts are sent via email when you exceed 85 percent of your usage for the month.

For more information, see:

* [What is AWS Billing and Cost Management?](http://What is AWS Billing and Cost Management?)
* [Using the AWS Free Tier](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-free-tier.html)
* [Getting started with AWS Cost Explorer](https://aws.amazon.com/blogs/aws-cloud-financial-management/getting-started-with-aws-cost-explorer-part-1/)

## Working in the Cloud

Although there are a wide range of services that researchers can use for developing and running analyses on AWS, there are several services that researchers generally use directly for research computing and for interacting with other AWS services. These are AWS Cloud9, Amazon Elastic Compute Cloud (EC2), and Amazon SageMaker. Each of these can be found in the AWS Management Console using the search interface at the top.

Each of these services give you access to a Linux terminal or shell, where you can install and update software tools and packages, update configuration files, and run commands. If you’re not already familiar with working with Linux, the guide [Unix Tutorial for Beginners](http://www.ee.surrey.ac.uk/Teaching/Unix/) will help you get started.

### AWS Cloud9

AWS Cloud9 is an integrated development environment, or *IDE*, which many users of AWS prefer for experimenting and working with other AWS services. Cloud9 offers an enhanced text editor for developing software applications, and a built-in Linux terminal. Although Cloud9 is primarily designed for software engineers, however, researchers typically find the integrated terminal and text editor interface to be helpful for building and running analyses on AWS.

Once you’ve created and logged into your AWS account, follow these steps to create a Cloud9 development environment:

1. Open the AWS Cloud9 console by going to https://console.aws.amazon.com/cloud9/
2. Choose the **Create environment** button.
3. On the **Name environment** page, for **Name**, enter a name for your environment. For example, `my-test-environment`. 
4. For **Description**, enter something about your environment. For example, `Cloud9 environment for testing
    `
5. Choose **Next step**. 
6. On the **Configure settings** page, the default settings will create a Cloud9 environment that can be accessed directly (via SSH, if needed), is free-tier eligible, and will auto-hibernate after 30 minutes in order to prevent unnecessary charges. These settings are generally suitable for new AWS users; however, you should review these settings to ensure they suit your needs.
7. Choose **Next step**. 
8. On the **Review** page, choose **Create environment**. Wait while AWS Cloud9 creates your environment. This can take several minutes. Once the environment has been created, your browser will be directed to the Cloud9 IDE.
9. For navigating the Cloud9 IDE, see [Tour the Cloud9 IDE](https://docs.aws.amazon.com/cloud9/latest/user-guide/tour-ide.html).

For more information on using Cloud9, see [Hello AWS Cloud9](https://docs.aws.amazon.com/cloud9/latest/user-guide/tutorial.html).

### AWS EC2

AWS EC2 enables researchers to provision and access Linux and Windows workstations in a matter of minutes, and to access them through a browser or using an SSH client (Linux), or via the Remote Desktop Protocol (Windows). EC2 offers numerous options for processor, storage, networking, operating system, and purchase models, to support a wide range of research needs.

To create a new EC2 instance, follow these steps:

1. Open the Amazon EC2 console by going to https://console.aws.amazon.com/ec2/
2. From the EC2 Console, click **Launch Instance**. 
3. The *Choose an Amazon Machine Image (AMI)* page displays a list of basic configurations called Amazon Machine Images (AMIs) that serve as templates for your instance. Click **Select** next to the *Amazon Linux 2 AMI* (first one).
4. On the *Choose an Instance Type* **** page, choose **t2.micro** as the hardware configuration of your instance, which is free-tier eligible, and click **Review and Launch**. 
5. On the *Review Instance Launch* page, Click **Launch**.
6. In the *Select an existing key pair or create a new key pair* dialog box, choose **Create a new key pair**, enter a name for the key pair, and then choose **Download Key Pair**. This is the only chance for you to save the private key file, so be sure to download it. Save the private key file in a safe place. You can use C:\user\yourusername.ssh\myfirstkey.pem if you are on a Windows machine, and ~/.ssh/myfirstkey.pem if you are on a Mac or Linux machine. You need to provide the name of your key pair when you launch an instance, and the corresponding private key each time you connect to the instance. 
7. A confirmation page lets you know that your instance is launching. Choose **View Instances** to close the confirmation page and return to the console.

Once your EC2 instance’s state is listed as *Running*, you can connect to the instance by following these steps:

1. Select the instances *instance id.*
2. On the *Instance summary* page, click the **Connect** button.
3. On the *Connect to instance* page, click the **Connect** button**.
    **

For additional hands-on instructions on setting up and using EC2 instances, see the [Amazon EC2 Workshop](https://ec2-immersionday.workshop.aws/).

### Amazon SageMaker

Amazon SageMaker is a service that enables data scientists and software developers to build, train, test, and deploy machine learning models. However, researchers broadly find SageMaker useful, as it provides a managed [Jupyter environment](https://jupyter.org/) that can be set up and accessed in a matter minutes, using a web browser.

To create and access a Jupyter Notebook using Amazon SageMaker, follow these steps:


1. Open the Amazon SageMaker console at https://console.aws.amazon.com/sagemaker/
2. Choose **Notebook instances**, and then choose **Create notebook instance**. 
3. On the **Create notebook instance** page, provide the following information (if a field is not mentioned, leave the default values): 
    1. For **Notebook instance name**, type a name for your notebook instance. 
    2. For **Instance type**, choose `ml.t2.medium`. This is the least expensive instance type that notebook instances support, and it suffices for this exercise. If a `ml.t2.medium` instance type isn't available in your current AWS Region, choose `ml.t3.medium`. 
    3. For **IAM role**, choose **Create a new role**, and then choose **Create role**. This IAM role automatically gets permissions to access any S3 bucket that has `sagemaker` in the name. It gets these permissions through the `AmazonSageMakerFullAccess` policy, which SageMaker attaches to the role. 
4. Choose **Create notebook instance**. In a few minutes, SageMaker launches the notebook instance in your browser.

For addition details, the tutorial [Get Started with Notebook Instances](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-setup-working-env.html)will guide you through the process of creating and access a Jupyter Notebook managed by SageMaker.

For additional AWS services that are typically used by researchers, see:

* [Awesome AWS Research](https://github.com/randyridgley/awesome-aws-research)
* [Introducing 10 minute cloud tutorials for research](https://aws.amazon.com/blogs/publicsector/introducing-10-minute-cloud-tutorials-research/)
* [AWS Research Workshops](https://github.com/aws-samples/aws-research-workshops)

## Storing data

In order to conduct analyses on AWS, you’ll first need to transfer any data that you wish to analyze to an AWS storage solution. There are a number of options for transferring and storing data on AWS; however, Amazon Simple Storage Service (S3) is the ideal choice for cost efficient, fast, and highly durable (very low chance of loss) data storage. S3 has a web-based interface that’s part of the AWS Management Console, and can an also be accessed via a local command line interface (terminal) and scripts for uploading, downloading, syncing, and managing files in S3.

Sign in to the preview version of the [AWS Management Console](https://console.aws.amazon.com/)

1. Open the Amazon S3 console at https://console.aws.amazon.com/s3/
2. From the Amazon S3 console dashboard, choose **Create Bucket**. 
3. In **Create a Bucket**, type a bucket name in **Bucket Name**.
    The bucket name you choose must be globally unique across all existing bucket names in Amazon S3 (that is, across all AWS customers). For more information, see [Bucket Restrictions and Limitations](http://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html).
4. Choose **Create**. When Amazon S3 successfully creates your bucket, the console displays your empty bucket in the **Buckets** pane. 

Once your S3 bucket has been created, you can upload files to the bucket by following these steps:

1. In the Amazon S3 console, choose the bucket where you want to upload an object, choose **Upload**, and then choose **Add Files**. 
2. In the file selection dialog box, find the file that you want to upload, choose it, choose **Open**, and then choose **Start Upload**. The progress of you upload will be displayed at the top of the page.

The quick start guide [Back Up Your Files to Amazon Simple Storage Service](https://docs.aws.amazon.com/quickstarts/latest/s3backup/welcome.html) provides addition information of storing and retrieving files using S3.

Files stored in S3 can be easily access from other AWS services, such as Cloud9, EC2, and SageMaker, for running computation and analyses on the data. The guide [Using Amazon S3 with Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonS3.html) covers how to use the AWS Command Line Interface (CLI) to transfer data stored in S3 to these services, for processing.

In order to ensure that services such as Cloud9 and EC2 have the permissions required to access your files in S3, see the guide:

* [IAM Policies and Bucket Policies and ACLs! Oh, My! (Controlling Access to S3 Resources)](https://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/)

## Using pre-packaged tools/services within AWS

AWS provides services that perform every function provided by physical hardware: compute, storage, networking, and many others. The ability to create and deploy individual services, or solutions built of multiple services, is often called *infrastructure as code*. This means that a resource, such as an EC2 instance functioning as a virtual server, can be defined in a few lines of code which can be used to create this resource using the AWS CloudFormation service. CloudFormation takes as input a text file in JSON or YAML format, which can define a solution of any complexity, and deploys the resources defined in that file. The CloudFormation template file can define not only the resources and their configuration, but the networking between them, and the permissions required for secure access.

To get started with CloudFormation, please refer to the [AWS CloudFormation Workshop](https://cfn101.workshop.aws/).

Another way to deploy existing tools is by launching a *Docker container*. A container is like a virtual server, but created from an *image* that holds some software and the configuration necessary to launch and run it. Pre-configured images containing popular software are readily available, and frequently contain software that performs one well-defined task, such as running a database server. You can create Docker images yourself, download them, or just link to an image made available on the internet. The Amazon Elastic Container service is used to launch and run a Docker container from that image, eliminating the need for installing the software on a bare server. You can control the size of the running container (CPU and memory), and link together multiple containers to create a more complex solution.

The [AWS Containers Immersion Day](https://containers-immersionday.workshop.aws/) can help you get started with using containers on AWS.
