* Adding an Issue Status: not working?

You have to edit the workflow AND uncheck the box that says " Only display statuses that are used by this tracker".

http://www.redmine.org/boards/2/topics/14738
http://www.redmine.org/projects/redmine/wiki/FAQ#Ive-created-a-new-issue-status-but-I-cant-use-it-it-doesnt-show-up-in-the-status-drop-down-list

* Bitnami Redmineのプラグイン

http://qiita.com/yashiooo/items/284926e331631cb3555a


* Redmine backup and restore

https://wiki.bitnami.com/Native_Installers_Quick_Start_Guide#How_can_I_create_a_full_backup_of_a_Stack.3f
http://redmine.jp/faq/system_management/backup/
https://amybughunter.wordpress.com/2013/01/22/migrating-your-redmine-instance-to-another-machine/

* redmine_backup.bat
<pre>
@echo off
set mydate=%date:/=%
set mytime=%time::=%
set outfiles=%mydate%_%mytime%_files
cd c:\Bitnami\bak\RedmineBak_DataFolder\
md %outfiles%
@set mysqldump="C:\Bitnami\redmine-2.6.10-3\mysql\bin\mysqldump" 
@set filename="redmine_backup.sql" 
@set file=%mydate%_%mytime%_%filename%
@set files="c:\Bitnami\redmine-2.6.10-3\apps\redmine\htdocs\files"
%mysqldump% -u <username> -p<password> bitnami_redmine > %file% 
xcopy %files% %outfiles% /c /e /i /y /z
robocopy "c:\Bitnami\bak\RedmineBak_DataFolder" "\\server\RedmineBak_DataFolder" /mir
</pre>
http://mattari.sumomo.ne.jp/2010/05/bitnami-redmine-%E3%81%AE%E3%83%90%E3%83%83%E3%82%AF%E3%82%A2%E3%83%83%E3%83%97%E3%82%92%E6%8E%A1%E3%81%A3%E3%81%A6%E3%81%BF%E3%81%9F/
