Start creating inventory (k8s-multinode-lab)

Run this from dotw-vagrant\labs\k8s-multinode-lab to capture SSH info, then we’ll paste it into inventory.

# 1) Capture vagrant SSH config for each VM
vagrant ssh-config k8s-multinode-lab-control-plane | Out-File -Encoding utf8 control-plane.sshconfig
vagrant ssh-config k8s-multinode-lab-worker        | Out-File -Encoding utf8 worker.sshconfig

# 2) Show key lines (HostName, Port, User, IdentityFile)
Select-String -Path .\control-plane.sshconfig -Pattern "HostName|Port|User|IdentityFile"
Select-String -Path .\worker.sshconfig        -Pattern "HostName|Port|User|IdentityFile"

Next, we’ll create dotw-ansible\inventories\vagrant\k8s-multinode-lab\hosts.yml using those values.

❓Paste the output of the two Select-String commands here and I’ll produce the exact hosts.yml content.