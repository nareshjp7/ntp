Role Name
=========

    This is only for installation ntp on over the client server using Asible using modelus of package or yum, tempalate and service.
    Using ntp for clock synchronisation between computer system over packate switched, variable latency data network.

Requirements
------------

    Requirements: knowledge over on templates, package and service using handlers.

Role Variables
--------------

    Using variable of 
        ntp_server1: dharmarao.node1.com
        ntp_server2: dharmarao.node2.com

Dependencies
------------

    None

Templates
---------

    #template file of ntp.j2

    ##NTP config - Managed using ansible

    driftfile /var/lib/ntp/drift
    restrict default nomodify notrap nopeer noquery
    restrict 127.0.0.1
    restrict ::1

    server {{ ntp_server1 }} iburst
    server {{ ntp_server2 }} iburst

    keys /etc/ntp/keys
    disable monitor


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    #Own NTP Role play
    # S Dharma Rao
    ---
    - name: Play role of ntp.management
        hosts: all
        become: yes
  
    roles:
        - ntp.management

License
-------

    SDR

Author Information
------------------

    S Dharma Rao
    dharmarao.samenu@outlook.com
