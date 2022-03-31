## Using Dockerfile
```bash
# build docker image.
docker build --build-arg ROOT_PASSWORD=password -t ssh_container .

# run docker container
docker run -itd --rm -p 2222:22 --name ssh_container ssh_container
```

## SSH Access
```
ssh root@localhost -p 2222
password: password
```

## Run ansible to specify an inventory
```
ansible -i ./hosts -m ping all --extra-vars "ansible_user=root ansible_password=password"
ansible-playbook main.yml  --extra-vars "ansible_user=root ansible_password=password"
```

## Read Later
- https://docs.ansible.com/ansible/latest/reference_appendices/general_precedence.html
- https://qiita.com/h_matsuno1028/items/33f06298d7d05bf1e295
- https://qiita.com/manabuishiirb/items/26de8c9740a1d2c7cfdd
