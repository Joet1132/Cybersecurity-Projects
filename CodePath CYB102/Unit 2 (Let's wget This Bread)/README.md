For this project, I was tasked with using the Linux Audit daemon to perform audit commands in order to:

1.) Configure a set of Audit rules to monitor file changes in ``/protected_files``

2.) Launch three attacks on some unknown files, and use Audit to identify the altered files and which attacks made the changes

My assignment for this project is to write down the names of the files modified by the attack scripts, and list ``(file, attack)`` pairings of which attack changed which file.

Files provided are from this starter repo ``wget https://github.com/codepath/project2/archive/main.zip`` that I downloaded while in the virtual machine.

3 separate ELF files are provided in the ZIP file, designed to modify a given file once executed. However, I needed to ``chmod`` the permissions for each of those 3 ELF files to enable execution.

In order to detect any changes done to the file we needed to keep track of, I have set watch rules by going into ``/etc/audit/rules.d/audit.rules`` using ``sudo vi'``

For each of the 10 files found in the ``/protected_files``, I set a watch on the required files to be monitored by using the ``auditctl`` command.
(e.g ``-w /home/codepath/project2-main/protected_files/car_sales.csv -p w -k protected_files_changes``)

After setting the watch rules, saving, and restarting the auditd service, I then began to run the scripts of attack-a, attack-b, and attack-c

Because I set the label tag ``-k protected_files_changes``, I was able to view the event log specific to those files altered by using: 
``sudo ausearch -k protected_files_changes``, and confirm which attacks changed which files.
