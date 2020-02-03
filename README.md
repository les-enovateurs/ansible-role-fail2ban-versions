Ansible Fail2ban-versions
=========
<p align="center">
  <a href="https://www.buymeacoffee.com/enovateurs" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-violet.png" height="41px" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
</p>

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should
be mentioned here. For instance, if the role uses the EC2 module, it may be a
good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including
any variables that are in defaults/main.yml, vars/main.yml, and any variables
that can/should be set via parameters to the role. Any variables that are read
from other roles and/or the global scope (ie. hostvars, group vars, etc.) should
be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in
regards to parameters that may need to be set for other roles, or variables that
are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: fail2ban-versions, x: 42 }

License
-------

BSD

Construct Image

<pre><font color="#CC0000">jeremy</font><font color="#D3D7CF">%</font> molecule test
--&gt; <font color="#06989A">Validating schema fail2ban-versions/molecule/default/molecule.yml.</font>
<font color="#4E9A06">Validation completed successfully.</font>
--&gt; <font color="#06989A">Test matrix</font>
    
└── default
    ├── lint
    ├── dependency
    ├── cleanup
    ├── destroy
    ├── syntax
    ├── create
    ├── prepare
    ├── converge
    ├── idempotence
    ├── side_effect
    ├── verify
    ├── cleanup
    └── destroy
    
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;lint&apos;</font>
--&gt; <font color="#06989A">Executing Yamllint on files found in fail2ban-versions/...</font>
<font color="#4E9A06">Lint completed successfully.</font>
--&gt; <font color="#06989A">Executing Flake8 on files found in fail2ban-versions/molecule/default/tests/...</font>
<font color="#4E9A06">Lint completed successfully.</font>
--&gt; <font color="#06989A">Executing Ansible Lint on fail2ban-versions/molecule/default/playbook.yml...</font>
<font color="#4E9A06">Lint completed successfully.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;dependency&apos;</font>
<font color="#C4A000">Skipping, missing the requirements file.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;cleanup&apos;</font>
<font color="#C4A000">Skipping, cleanup playbook not configured.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;destroy&apos;</font>
--&gt; <font color="#06989A">Sanity checks: &apos;docker&apos;</font>
    
    PLAY [Destroy] *****************************************************************
    
    TASK [Destroy molecule instance(s)] ********************************************
    <font color="#C4A000">changed: [localhost] =&gt; (item=instance)</font>
    
    TASK [Wait for instance(s) deletion to complete] *******************************
    <font color="#555753"><b>FAILED - RETRYING: Wait for instance(s) deletion to complete (300 retries left).</b></font>
    <font color="#4E9A06">ok: [localhost] =&gt; (item=None)</font>
    <font color="#4E9A06">ok: [localhost]</font>
    
    TASK [Delete docker network(s)] ************************************************
    
    PLAY RECAP *********************************************************************
    <font color="#C4A000">localhost</font>                  : <font color="#4E9A06">ok=2   </font> <font color="#C4A000">changed=1   </font> unreachable=0    failed=0    <font color="#06989A">skipped=1   </font> rescued=0    ignored=0
    
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;syntax&apos;</font>
--&gt; <font color="#06989A">Sanity checks: &apos;docker&apos;</font>
    
    playbook: fail2ban-versions/molecule/default/playbook.yml
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;create&apos;</font>
    
    PLAY [Create] ******************************************************************
    
    TASK [Log into a Docker registry] **********************************************
    <font color="#06989A">skipping: [localhost] =&gt; (item=None) </font>
    
    TASK [Create Dockerfiles from image names] *************************************
    <font color="#C4A000">changed: [localhost] =&gt; (item=None)</font>
    <font color="#C4A000">changed: [localhost]</font>
    
    TASK [Determine which docker image info module to use] *************************
    <font color="#4E9A06">ok: [localhost]</font>
    
    TASK [Discover local Docker images] ********************************************
    <font color="#4E9A06">ok: [localhost] =&gt; (item=None)</font>
    <font color="#4E9A06">ok: [localhost]</font>
    
    TASK [Build an Ansible compatible image (new)] *********************************
    <font color="#4E9A06">ok: [localhost] =&gt; (item=molecule_local/debian:jessie)</font>
    
    TASK [Build an Ansible compatible image (old)] *********************************
    <font color="#06989A">skipping: [localhost] =&gt; (item=molecule_local/debian:jessie) </font>
    
    TASK [Create docker network(s)] ************************************************
    
    TASK [Determine the CMD directives] ********************************************
    <font color="#4E9A06">ok: [localhost] =&gt; (item=None)</font>
    <font color="#4E9A06">ok: [localhost]</font>
    
    TASK [Create molecule instance(s)] *********************************************
    <font color="#C4A000">changed: [localhost] =&gt; (item=instance)</font>
    
    TASK [Wait for instance(s) creation to complete] *******************************
    <font color="#555753"><b>FAILED - RETRYING: Wait for instance(s) creation to complete (300 retries left).</b></font>
    <font color="#C4A000">changed: [localhost] =&gt; (item=None)</font>
    <font color="#C4A000">changed: [localhost]</font>
    
    PLAY RECAP *********************************************************************
    <font color="#C4A000">localhost</font>                  : <font color="#4E9A06">ok=7   </font> <font color="#C4A000">changed=3   </font> unreachable=0    failed=0    <font color="#06989A">skipped=3   </font> rescued=0    ignored=0
    
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;prepare&apos;</font>
<font color="#C4A000">Skipping, prepare playbook not configured.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;converge&apos;</font>
    
    PLAY [Converge] ****************************************************************
    
    TASK [Gathering Facts] *********************************************************
    <font color="#4E9A06">ok: [instance]</font>
    
    TASK [fail2ban-versions : Update APT] ******************************************

    <font color="#C4A000">changed: [instance]</font>
    
    TASK [fail2ban-versions : Install dependencies] ********************************
    <font color="#C4A000">changed: [instance]</font>
    
    TASK [fail2ban-versions : Git clone fail2ban] **********************************
    <font color="#4E9A06">ok: [instance]</font>
    
    TASK [fail2ban-versions : Execute Script] **************************************
    <font color="#4E9A06">ok: [instance]</font>
    
    TASK [fail2ban-versions : Install global configuration of fail2ban] ************
    <font color="#C4A000">changed: [instance]</font>
    
    TASK [fail2ban-versions : Template files] **************************************
    <font color="#06989A">skipping: [instance] =&gt; (item=fail2ban-versions/templates/filters/wordpress-xmlrpc-nginx.conf) </font>
    <font color="#C4A000">changed: [instance] =&gt; (item=fail2ban-versions/templates/filters/wordpress-xmlrpc-apache.conf)</font>
    
    TASK [fail2ban-versions : Check status of fail2ban] ****************************
    <font color="#CC0000">fatal: [instance]: FAILED! =&gt; {&quot;changed&quot;: false, &quot;cmd&quot;: [&quot;fail2ban-client&quot;, &quot;status&quot;], &quot;delta&quot;: &quot;0:00:00.484857&quot;, &quot;end&quot;: &quot;2019-08-19 14:46:34.417955&quot;, &quot;msg&quot;: &quot;non-zero return code&quot;, &quot;rc&quot;: 255, &quot;start&quot;: &quot;2019-08-19 14:46:33.933098&quot;, &quot;stderr&quot;: &quot;2019-08-19 14:46:34,417 fail2ban                [6190]: ERROR   Failed to access socket path: /var/run/fail2ban/fail2ban.sock. Is fail2ban running?&quot;, &quot;stderr_lines&quot;: [&quot;2019-08-19 14:46:34,417 fail2ban                [6190]: ERROR   Failed to access socket path: /var/run/fail2ban/fail2ban.sock. Is fail2ban running?&quot;], &quot;stdout&quot;: &quot;&quot;, &quot;stdout_lines&quot;: []}</font>
    <font color="#06989A">...ignoring</font>
    
    TASK [fail2ban-versions : Start fail2ban-client] *******************************
    <font color="#C4A000">changed: [instance]</font>
    
    TASK [fail2ban-versions : Clean clone directory tmp fail2ban repository] *******
    <font color="#4E9A06">ok: [instance]</font>
    
    TASK [Check fail2ban-client works] *********************************************
    <font color="#4E9A06">ok: [instance]</font>
    
    TASK [Check extension every plugins install] ***********************************
    <font color="#4E9A06">ok: [instance] =&gt; (item=wordpress-xmlrpc-apache)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-auth)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-badbots)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-noscript)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-overflows)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-nohome)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-botsearch)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-fakegooglebot)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-modsecurity)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=apache-shellshock)</font>
    <font color="#4E9A06">ok: [instance] =&gt; (item=zoneminder)</font>
    
    PLAY RECAP *********************************************************************
    <font color="#C4A000">instance</font>                   : <font color="#4E9A06">ok=12  </font> <font color="#C4A000">changed=5   </font> unreachable=0    failed=0    skipped=0    rescued=0    <font color="#AD7FA8"><b>ignored=1   </b></font>
    
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;idempotence&apos;</font>
<font color="#4E9A06">Idempotence completed successfully.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;side_effect&apos;</font>
<font color="#C4A000">Skipping, side effect playbook not configured.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;verify&apos;</font>
--&gt; <font color="#06989A">Executing Testinfra tests found in fail2ban-versions/molecule/default/tests/...</font>
    <b>============================= test session starts ==============================</b>
    platform linux -- Python 3.6.8, pytest-5.1.0, py-1.8.0, pluggy-0.12.0
    rootdir: fail2ban-versions/molecule/default
    plugins: testinfra-3.1.0
<b>collected 1 item                                                               </b>
    
    tests/test_default.py <font color="#4E9A06">.</font><font color="#06989A">                                                  [100%]</font>
    
    <font color="#8AE234"><b>============================== 1 passed in 3.48s ===============================</b></font>
<font color="#4E9A06">Verifier completed successfully.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;cleanup&apos;</font>
<font color="#C4A000">Skipping, cleanup playbook not configured.</font>
--&gt; <font color="#06989A">Scenario: &apos;default&apos;</font>
--&gt; <font color="#06989A">Action: &apos;destroy&apos;</font>
    
    PLAY [Destroy] *****************************************************************
    
    TASK [Destroy molecule instance(s)] ********************************************
    <font color="#C4A000">changed: [localhost] =&gt; (item=instance)</font>
    
    TASK [Wait for instance(s) deletion to complete] *******************************
    <font color="#555753"><b>FAILED - RETRYING: Wait for instance(s) deletion to complete (300 retries left).</b></font>
    <font color="#C4A000">changed: [localhost] =&gt; (item=None)</font>
    <font color="#C4A000">changed: [localhost]</font>
    
    TASK [Delete docker network(s)] ************************************************
    
    PLAY RECAP *********************************************************************
    <font color="#C4A000">localhost</font>                  : <font color="#4E9A06">ok=2   </font> <font color="#C4A000">changed=2   </font> unreachable=0    failed=0    <font color="#06989A">skipped=1   </font> rescued=0    ignored=0
    
--&gt; <font color="#06989A">Pruning extra files from scenario ephemeral directory</font>
</pre>
