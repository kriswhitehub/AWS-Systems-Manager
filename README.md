# AWS-Systems-Manager
AWS Systems Manager- Automating Patch Management With AWS Systems Manager
1. Logging In to the Amazon Web Services Console
2. Attaching the SSM Policy to an IAM Role
3. Connecting to the Virtual Machine using EC2 Instance Connect
4. Installing the AWS Systems Manager Agent
5. Running a Patch Scan


### Patching

#### AWS Linux Systems

1. Inventory Management
    * Use AWS Systems Manager to automatically discover and manage your Linux instances on AWS.
    * Categorize instances by environment, application, or other criteria to tailor patching schedules.

2. Patch Baseline Configuration
    * Define a patch baseline in AWS Systems Manager Patch Manager for your Linux distributions (e.g., Amazon Linux, Ubuntu). This includes specifying approved or rejected patches and patch compliance levels.
    * Assign the patch baseline to your instance groups based on the categories defined earlier.

3. Automation and Scheduling
    * Schedule patching windows using Maintenance Windows in AWS Systems Manager, ensuring minimal impact on production workloads.
    * Automate patch deployment to automatically apply approved patches during these windows.

4. Testing
    * Use a subset of instances or a staging environment to test patches before wide-scale deployment.
    * Monitor for issues and rollback if necessary using AWS Systems Manager automation documents.

5. Compliance Monitoring and Reporting
    * Utilize AWS Systems Manager Compliance to monitor and report on patch compliance across your Linux instances.
    * Address any non-compliant instances promptly to ensure security and compliance.

#### On-premises Linux Systems
1. Inventory Management
    * Utilize a configuration management database (CMDB) or inventory tool to maintain an up-to-date list of Linux servers and their roles.
    * Group servers by function, application, or environment for targeted patching.

2. Patch Baseline Configuration
    * Define a patch policy that outlines the frequency of patching, types of patches (security, critical updates), and exceptions.
    * Establish a process for reviewing and approving patches before deployment.

3. Patch Deployment
    * Utilize patch management tools (e.g., Red Hat Satellite, Spacewalk, or Landscape) to deploy patches. Consider open-source tools like Ansible for automation.
    * Schedule patch deployments during off-peak hours to minimize impact. Ensure patches are applied in a staged manner, starting with development, then staging, and finally production environments.

4. Testing
    * Test patches on a representative sample of systems before broad deployment.
    * Monitor system and application logs for issues post-patch and have a rollback plan in place.

5. Compliance Monitoring and Reporting
    * Regularly audit systems for patch compliance using your chosen patch management tool or custom scripts.
    * Generate compliance reports for internal and external audit purposes. Address any compliance issues immediately.
## Role Back Plan

### Rollback Plan for AWS Linux Systems

1. Pre-Deployment Preparations

      * Ensure that you have a recent backup of the system and data. Utilize AWS Backup or your preferred backup solution to create snapshots or backups of your instances and volumes.
      * Test the backup restoration process regularly to confirm that you can quickly revert to a pre-patch state if necessary.

2. Automated Rollback Using AWS Systems Manager

      * Use AWS Systems Manager State Manager to create a document that specifies the pre-patch state of the instances or uses previously known good configurations.
      * In the event of a failed patch deployment, trigger the State Manager document to revert the instances to their previous configurations.

3. Manual Rollback Procedures

      * If automated rollback is not feasible, manually stop the affected instances.
      * Restore from the pre-patch backups or snapshots to revert the instances to their pre-patch state.
      * Restart the instances and validate that the services are running as expected.

4. Post-Rollback Actions

      * Analyze logs and monitoring data to understand the cause of the issue.
      * Implement necessary changes to avoid similar issues in future patch deployments.

### Rollback Plan for On-premises Linux Systems
1. Pre-Deployment Preparations

      * Ensure comprehensive backups are taken before patching, including system states, application data, and databases.
      * Validate the backup integrity and restoration process periodically.

2. Using Configuration Management Tools for Rollback

      * Utilize configuration management tools (e.g., Ansible, Puppet, Chef) to snapshot the system state before applying patches. These tools can also be used to automate the rollback process.
      * In case of a patch issue, use these tools to apply the pre-patch configuration to the servers.

3. Manual Rollback Procedures

      * If automated tools are not in place or fail, manually remove the problematic patches using package managers like yum or apt-get to revert to previous versions of the packages.
      * For more severe issues, restore the systems from the backups taken before patching. This might involve re-imaging the server and restoring data from backups.

4. Post-Rollback Actions

      * Conduct a thorough investigation to identify the cause of the failure. This might involve reviewing patch notes, system logs, and application logs.
      * Adjust the patch testing and deployment process to prevent recurrence of the issue.
