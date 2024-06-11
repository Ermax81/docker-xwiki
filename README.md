This project aims to provide a simple way to deploy XWiki using Docker.

XWiki is a free wiki software platform written in Java. It runs on a servlet container like Tomcat and uses a database such as MySQL to store its information.

## Sources:

You will find below some usefull links.
- [xwiki-docker repository on Github.com](https://github.com/xwiki/xwiki-docker/blob/master/README.md)
- [Deploy example with postgres](https://github.com/xwiki/xwiki-docker/blob/master/15/postgres-tomcat/docker-compose.yml)
- [Obsolete docker example from zwindle](https://github.com/zwindler/docker-xwiki)
- [Deploy xwiki on Synology NAS with docker 2021-04-17](https://www.christian-knedel.de/fr/post/2021/april/20210417-docker-xwiki/)
- [Fork of docker-xwiki](https://github.com/kemelinux/docker-xwiki)
- [Best Practice Xwiki Docker Installation](https://forum.xwiki.org/t/best-practice-xwiki-docker-installation/5502)
- [Deploy Xwiki 8.2.1 with postgres 2016-09-15](https://blog.zwindler.fr/2016/09/15/installer-xwiki-8-2-1-avec-docker-compose-en-2-lignes-de-commandes/)
- [Installer XWiki avec Docker 2020-03-03 Oana Elena Florea](https://xwiki.com/fr/Blog/Installer-XWiki-avec-Docker/)
- [How to install XWiki using Docker 2020-02-13 Oana Elena Florea](https://xwiki.com/en/Blog/HowtoinstallXWikiusingDocker/)

## More information about Solr

By default XWiki ships with an embedded Solr. 
This is mostly for ease of use but the embedded instance is not really recommended by the Solr team so you might want to externalize it when starting to have a wiki with a lots of pages. Solr is using a lot of memory and a standalone Solr instance is generally better in term of speed than the embedded one. It should not be much noticeable in a small wiki but if you find yourself starting to have memory issues and slow search results you should probably try to install and setup an external instance of Solr using the guide.

## How to delete the volumes

```bash 
docker volume rm docker-xwiki_postgres-data docker-xwiki_xwiki-data
```