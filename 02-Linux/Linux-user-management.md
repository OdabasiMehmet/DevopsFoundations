Linux is an operating system that provides a vast array of tools and utilities for managing users and their accounts. Le’s take a look at some common user management tasks.

## Adding a User
The first step in user management is to add a new user to the system. This can be done with the useradd or adduser command. The syntax is simple:

```bash
sudo useradd [username]
```

By default, this will create a new user with a home directory, a default shell, and no password. To verify the user, we can check /etc/passwd folder.

```bash
sudo cat /etc/passwd
```

If we want to set a password for the new user, we can use the passwd command:

```bash
sudo passwd [username]
```

We need to enter a password and then retype it to make sure password is set.


## Deleting a User
To delete a user, use the userdel command. This will delete the user account .

```bash
sudo userdel [username]
```

To verify whether the user is deleted, we can check /etc/passwd folder.
```bash
sudo cat /etc/passwd
```

If you want to delete the user’s home directory as well, use the -r option with userdel command.

```bash
sudo userdel -r [username]
```

## Changing user
To switch to another user account, use the su command.

```bash
su [username]
```

Let’s verify that we changed the user with whoami command.

```bash
whoami
```

The - option with su command is used to run a login shell for the target user, which means that the environment and current working directory will be changed to reflect the target user's account.

```bash
su [username] -
```
This will prompt for the target user’s password and then switch to their account, creating a login shell for them.

## Managing User Groups
In Linux, users can be organized into groups. This allows you to manage permissions and access to resources on a per-group basis.

## Creating a group
To create a group, use the groupadd command:

```bash
sudo groupadd [groupname]
```

To check the groups, we can cat the group folder under etc.
```bash
sudo cat /etc/group
```

To add a user to a group, use the usermod command:

```bash
sudo usermod -a -G [group] [username]
```

Then you can check /etc/group to see whether the user is added to group

```bash
sudo cat /etc/group
```

To view a list of groups a user is a member of, use the groups command:

```bash
groups [username]
```

## Deleting a group
To delete a group, we can use groupdel command

```bash
sudo groupdel groupname
```

## Gathering information about a user
To display information about a user’s account, including the user’s user ID (UID), group ID (GID), and group membership, we can use id command.


```bash
# for root user
id 
# for a specific user
id username
```

## Ownership
To changes the owner of a file or directory, we can use chown command.

```bash
sudo chown [username]:[groupname] [file/directory]
```
