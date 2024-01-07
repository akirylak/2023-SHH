# SANS HOLIDAY HACK 2023: SimonCypherSays Report
## Chapter 5 Challenge: Azure 101
### Location: Christmas Island / Rudolph’s Rest
Following the path to the left, we come across our second challenge in Rudolph’s Rest titled Azure 101. There is a big crowd here tonight surrounding the challenge. I hope the majority of these users are doing just as well as I am with completing these challenges. I still wonder why I look like I have a half-melted marshmallow as a hat. Personally, I prefer to wear an aviator hat.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-1.png)

Opening the Azure CloudShell, we type in our first prompt to start the challenge: ```az help | less```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-2.png)

We are provided a list of commands that will be useful for us to complete this challenge. The prompt gives us the next set of instructions to complete the second part of the challenge. This command is very straight forward as we will use az account show | less .

However, we need to quit the help page by using the ```q``` character to bring us back to the shell window.
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-3.png)

**Next, you've already been configured with credentials. Use 'az' and your 'account' to 'show' your current details and make sure to pipe to less ( | less )**
Follow the instructions provided in the prompt by using ```az account show | less```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-4.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-5.png)

**Excellent! Now get a list of resource groups in Azure. For more information: https://learn.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest**

Reviewing the documentation microsoft provides, we will use the command ```az group list | less```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-6.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-7.png)

Use the q character to quit and go back to the Azure shell.

**Ok, now use one of the resource groups to get a list of function apps. For more information: https://learn.microsoft.com/en-us/cli/azure/functionapp?view=azure-cli-latest**
**Note: Some of the information returned from this command relates to other cloud assets used by Santa and his elves.**

Reviewing the documentation microsoft provides, we will use the command ```az functionapp list --resource-group northpole-rg1```

![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-8.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-9.png)

**Find a way to list the only VM in one of the resource groups you have access to. For more information:https://learn.microsoft.com/en-us/cli/azure/vm?view=azure-cli-latest**

Reviewing the documentation microsoft provides, we will use the command ```az vm list --resource-group northpole-rg2```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-10.png)
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-11.png)

**Find a way to invoke a run-command against the only Virtual Machine (VM) so you can RunShellScript and get a directory listing to reveal a file on the Azure VM. For more information:**
**https://learn.microsoft.com/en-us/cli/azure/vm/run-command?view=azure-cli-latest#az-vm-run-command-invoke**

Reviewing the documentation microsoft provides, we will use the command ```az vm run-command invoke -g northpole-rg2 -n NP-VM1 --command-id RunShellScript --scripts "ls" --output table```
![](https://github.com/akirylak/2023-SHH/blob/main/Chapter%205%20-%20Azure101/Chapter5-12.png)
