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

* redmine add field and apply

http://redmine.jp/glossary/c/custom-field/

* Using redmine effectively

Daily Status and Client Meeting Minutes Ticket per iteration.

You can create an issue daily status per iteration and this issue will be updated daily in that iteration . The team status on each day , issues faced , work done will be updated in that ticket . This will help to keep the work don in a iteration documented respective daily status ticket. Having such tickets per iteration helps to keep the ticket modular or else after few iterations, the ticket will contain so may updates and it might decrease the readers interest .

Link to Git or SVN

svn ci -m "incorrect encoding fixed (refs #2345)"

In fact the idea of this is to be able to make connection between some issue and svn revisions related to it. It should work both ways - in repository page you see the link to the issue; in the issue's page you should be able to see the link to the related revisions.
For this to work you need:
to have configured repository in your project (or parent project, it works as well)
to have configured keywords like refs in Administration->Settings [Repository] ->"Referencing keywords"
when you commit to svn (mentioning your issue in commit description like "refs #1234"), this revision doesn't appear automatically in redmine repository - you need to refresh it manually going to Repository tab of the project (it's possible to make it automatic with some cron jobs).
After all this you should be able to see in your issue "Associated revisions"

https://stackoverflow.com/questions/3607590/best-way-to-link-redmine-issue-to-svn-revision

https://it-consultis.com/blog/10-ultimate-redmine-tips

https://kodgiresuhas.wordpress.com/2013/04/10/how-to-use-redmine-effectively/

http://stackoverflow.com/questions/232506/redmine-best-practices


* Redmine and git on windows

http://d.hatena.ne.jp/doc1oo/20091010/1255147850

http://qiita.com/Sakade3346/items/7363a32c3db305e3313a

* 注意设定到服务器上bare git repo，这样就无需担心redmine没有更新
http://www.saintsjd.com/2011/01/what-is-a-bare-git-repository/

* Install 「Redmine Issue Importer」

http://liginc.co.jp/web/tutorial/111766

https://github.com/zh/redmine_importer/

* Redmine roadmap plugin

http://aws.aipo.com/blog/2015/01/30_122601.html

http://www.redmine.org/plugins/advanced_roadmap_v2
