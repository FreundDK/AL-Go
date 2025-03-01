# #5 Register a customer production environment for Manual Deployment
*Prerequisites: A completed [scenario 4](CreateRelease.md), an online production environment setup for S2S as specified in task 2 here [Using Service to Service Authentication - Business Central | Microsoft Docs](https://go.microsoft.com/fwlink/?linkid=2217415&clcid=0x409), using the same AAD App as scenario 3*

***Note**: Environments are only supported in public repositories or with GitHub Enterprise license (see [this](https://go.microsoft.com/fwlink/?linkid=2216857&clcid=0x409)). We are considering adding a secondary option for listing environments.*
1. Following the process in step 3, you can add an environment to the GitHub repository under settings called **MYPROD (Production)** (the name of your production environment followed by “ (Production)”), which maps to a production environment called **MYPROD**. Remember the **AUTHCONTEXT** Secret. Apps will NOT be deployed to production environments from the CI/CD pipeline, by adding the **(Production)** tag, the environment will be filtered out already during the **Analyze** phase. You need to run the **Publish To Environment** workflow to publish the apps. Leave the App version as **current**, which means that the **latest released bits** are published to **MYPROD**.
![Run workflow](images/5a.png)
1. After running the **Publish to Environment** workflow, you should see that the app was deployed to the **MYPROD** environment only.
![Run workflow](images/5b.png)

---
[back](../README.md)
