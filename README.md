rnilekani@python-server:~# ansible-playbook router.yml --check

PLAY [local] ****************************************************************** 

GATHERING FACTS *************************************************************** 
ok: [localhost]

TASK: [Generate Arista Configuration file.] *********************************** 
changed: [localhost] => (item={'hostname': 'arista-rtr1', 'ip_addr': '1.1.1.1'})
changed: [localhost] => (item={'hostname': 'arista-rtr2', 'ip_addr': '1.1.1.2'})
changed: [localhost] => (item={'hostname': 'arista-rtr3', 'ip_addr': '1.1.1.3'})
changed: [localhost] => (item={'hostname': 'arista-rtr4', 'ip_addr': '1.1.1.4'})

PLAY RECAP ******************************************************************** 
localhost                  : ok=2    changed=1    unreachable=0    failed=0   

rnilekani@python-server:~# ansible-playbook router.yml

PLAY [local] ****************************************************************** 

GATHERING FACTS *************************************************************** 
ok: [localhost]

TASK: [Generate Arista Configuration file.] *********************************** 
changed: [localhost] => (item={'hostname': 'arista-rtr1', 'ip_addr': '1.1.1.1'})
changed: [localhost] => (item={'hostname': 'arista-rtr2', 'ip_addr': '1.1.1.2'})
changed: [localhost] => (item={'hostname': 'arista-rtr3', 'ip_addr': '1.1.1.3'})
changed: [localhost] => (item={'hostname': 'arista-rtr4', 'ip_addr': '1.1.1.4'})

PLAY RECAP ******************************************************************** 
localhost                  : ok=2    changed=1    unreachable=0    failed=0   

rnilekani@python-server:~# ls
arista-rtr1.txt  arista-rtr2.txt  arista-rtr3.txt  arista-rtr4.txt  router.j2  router.yml
root@python-server:~# cat arista-rtr1.txt
!
hostname arista-rtr1
!
spanning-tree mode mstp
!
no aaa root
!
int Ethernet1
 no switchport
 ip address 1.1.1.1

ip routing






