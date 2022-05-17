# Setup guide

## Initial steps

```bash
xcode-select --install
sudo xcodebuild -license
# if u are on the arm arch
/usr/sbin/softwareupdate --install-rosetta
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py
sudo pip3 install --ignore-installed ansible
ansible-galaxy install -r roles/setup_macos/requirements.yml
```

## Running playbook

```bash
ansible-playbook -i inventories/localhost roles/setup_macos/playbook.yml --ask-become-pass
```

## Running only tags

```bash
ansible-playbook -i inventories/localhost roles/setup_macos/playbook.yml --ask-become-pass --tags "rollback-to-bash"
```
