# AWS-Systems-Manager
AWS Systems Manager- Automating Patch Management With AWS Systems Manager
1. Logging In to the Amazon Web Services Console
2. Attaching the SSM Policy to an IAM Role
3. Connecting to the Virtual Machine using EC2 Instance Connect
4. Installing the AWS Systems Manager Agent
5. Running a Patch Scan

### AWS Linux Systems

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
