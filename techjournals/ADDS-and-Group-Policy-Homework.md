### Question 1:

In dealing with Group Policy, what are two commands and their use for verifying and
troubleshooting group policies applied by a Domain Controller?

**Answer:**

* gpresult:

This command is used to display the Resultant Set of Policy(RSoP) or which group policies and settings are currently applied

**Current user syntax:** 

gpresult /user <username> /h <path\to\output\file.html>

**Specific computer syntax:**

gpresult /computer <computername> /h <path\to\output\file.html>

* gpupdate

This command is used to force an immediate update of group policy settings if they have not been updates/applied

**Syntax:**

gpupdate /force

### Question 2:

When are COMPUTER group policy settings applied, and when are USER group policy
settings applied?

**Answer:**

Computer and Group Policies are applied differently in different times/circumstances

**Computer Group Policy**

* During Startup

* Every 90 Minutes

* When Forced

**User Group Policy**

* During User Logon

* Every 90 Minutes

* When Forced
### Question 3:

Within a Windows Domain, why is it important that Domain Controllers replicate Active
Directory information?

**Answer:**

This is important for multiple reasons such as:
* High Availability and Redundancy
* Load Balancing
* Reduced Network Latency
* Fault Tolerance
* Support for Multi-site environments
* Consistency and Data Integrity
* Scalability
* Disaster Recovery
* Efficient Updates

### Question 4:

What is the purpose of an Organizational Unit?

**Answer:**

The purpose of an OU in AD is to provide a flexible and hierarchal structure for maintaining admin control, applying policies, and managing permissions for resources

### Question 5:

You have a group policy setup and want to test it on a particular account or computer before
making changes everywhere? How could you accomplish this?

**Answer:**

To test a group policy before applying it globally you can use Global Policy Filtering. This allows you to target specific users, groups, or computers

The steps to this are:
1. Create or Identify the Group Policy Object
2. Edit the GPO
3. Configure GPO settings
4. Filter the GPO
5. Test the Filters