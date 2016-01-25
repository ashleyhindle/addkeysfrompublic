# addkeys
Simple script to allow you to easily setup authorised key files from publicly accessible SSH keys - Primarily GitHub and GitLab instances.

This is really useful for automated server provisioning - this can easily be added to your Linode StackScript, Ansible/Puppet/Salt scripts or bash provisioning scripts.

# Usage
| Short Option | Long Option | Description | Example |
| ------------ | ----------- | ----------- | ------- |
| -f | --file | Which authorized key file to use | /root/.ssh/authorized_keys |
| -u | --usernames | Comma separated list of usernames to process, with no whitespace | bob,jill,tony |
| -b | --baseurl | Base url to retrieve keys from, defaults to https://github.com/ | https://gitlab.mycompany.com |
| -p | --perms | Don't set the authorized key files permissions to 600 |  |
| -v | --verbose | Output the keys being added |  |
| -h | --help | Output the usage information |  |

# Download
`curl -s -o ./addkeys http://addkeys.ashleyhindle.com/addkeys; chmod a+x addkeys` (HTTPs incoming)

# Examples
**Add my SSH keys to roots authorized keys file**  
`./addkeys -f /root/.ssh/authorized_keys -u ashleyhindle`


**Add my coworkers keys to roots authorized keys file, from my company's private gitlab instance**  
`./addkeys -b https://gitlab.mycompany.com/ -f /root/.ssh/authorized_keys -u bob,jill,tony`
