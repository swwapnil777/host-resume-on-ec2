![Screenshot 2024-03-01 220147](https://github.com/swwapnil777/host-resume-on-ec2/assets/108779988/7dd07f09-77e4-4381-bd4b-dc8f99f444f7)

# EC2 Deployment with GitHub Actions

This repository contains a GitHub Actions workflow that automates the deployment of code to an EC2 instance upon pushing changes to the master branch. The workflow uses SSH to connect to the EC2 instance and execute deployment commands.

## Workflow Description

The workflow is triggered by push events to the master branch. Upon trigger, it performs the following steps:

1. **Checkout the Files**: The workflow checks out the code from the repository.

2. **Deploy to EC2 Instance**: It uses the SSH deploy action to connect to the EC2 instance using SSH and deploy the code. The necessary SSH credentials are stored as GitHub secrets.

3. **Execute Remote Commands**: The workflow then uses another SSH action to execute remote commands on the EC2 instance. In this case, it updates the package repository, installs Apache HTTP Server, starts the Apache service, and moves the deployed files to the web server directory.

## Workflow Setup

To set up a similar workflow for your repository, follow these steps:

1. Ensure you have an EC2 instance set up and running.

2. Generate an SSH key pair and add the public key to the EC2 instance for authentication.

3. Store the private key and other sensitive information (such as the EC2 instance DNS, username, and target directory) as GitHub secrets in your repository settings.

4. Copy the provided GitHub Actions workflow file (`.github/workflows/main.yml`) into your repository.

5. Update the workflow file to match your specific setup. You may need to adjust the commands depending on your deployment requirements.

6. Push the changes to your repository's master branch to trigger the workflow.

## Security Considerations

- Ensure that sensitive information like SSH keys and server credentials are stored securely as GitHub secrets and not exposed in your repository.

- Limit access to the repository and secrets only to authorized users or teams.

- Regularly review and rotate credentials to maintain security.

## Contribution

Contributions to enhance or improve this workflow are welcome! If you find any issues or have suggestions, please open an issue or submit a pull request.


