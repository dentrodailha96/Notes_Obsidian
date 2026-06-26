# Manual concepts

- pwd : print working directory.

## Local vs Global changes

**Global**: programs/environments that any user can use, used across the system. 
**Local or By user**: programs/environments that a particular user runs, not available to other users. 

## Linux users: 

- **root**: the powerful superuser that can execute any command at any level in the system.
- **sudoers**: regular users that are allowed to use sudo, they can execute commands in one or more levels in the system, can do some or all global changes.
- **regular users**: users that can use the system but can only do local changes.

### create a new user
- add {user name}
- usermod -a -G sudo {user name}
  > usermod (modifies a user account).
  > -a (append)
  > -G sudo (adds the user to the sudo group)

### Change password
- passwd

### Switch users
- su {user_name}

### sudo command 
- Super command to get access to system files that usually only admin or root users have.
  > sudo -i (sudo interactive - launches a new login shell for the root user,
  creating a new environment for the root user with the user's home directory and shell config files).
  > sudo -s (sudo shell, launches a new shell for the root user, but it does not create a new login shell.
  Therefore, does not change the env or shell config from current user. 

_sudo -s ≈ Container_

- Shares the host environment (your user's vars, PATH)
- Just elevates privileges on top of what's already there
- Lightweight, quick, inherits context
- Like a container sharing the host kernel but with its own process

_sudo -i ≈ VM_

- Fresh, isolated environment (root's own HOME, PATH, profile)
- Boots up cleanly, doesn't care about what you had before
- More "complete" and self-contained
- Like a VM with its own full OS layer

### create empty file 

- touch

### get the timezone from the computer 
- timedatectl
- timedatectl list-timezones (get all the timezones).
- sudo timedatectl set-timezone {timezone choice}.

**Good practice**:  it’s important to take the necessary precautions before making global changes, to prevent accidentally locking yourself out or other issues. 
Practices like using a test environment, checking for syntax errors and typos, and keeping an eye on the log files, will eventually become second nature.

