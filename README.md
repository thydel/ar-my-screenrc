# [Install my-screnrc with Ansible](https://github.com/thydel/ar-my-screenrc)

- Install a screenrc template
- Crypt and use a password if requested (use no_log)
  
## Usage

Install via [Galaxy](https://galaxy.ansibleworks.com/):

```bash
ansible-galaxy install thydel.my-screenrc
```

Or use from local clone:

```bash
sudo aptitude install whois # mkpasswd
screenrc-play.yml -i locahost, -c local -D
```

## Role Variables

`screen_password` is the clear text password presumably from vault or
vars_prompt. Ignored by template if undefined or empty string.

## Example Playbook

```yaml
- hosts: all
  user: thy
  vars_prompt:
    - name: screen password
      prompt: screen_password
      private: yes
  roles:
	- thydel.my-screenrc
```

## Notes

- Should take user as parameter
- Should allow use of user system password
- Could allow multiple user setup
- Could allow multiple screenc switch
- Could allow parametric predefined screen context

