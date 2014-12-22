autoconf-archive-rpm
====================

Create RPM package for [autoconf-archive](http://www.gnu.org/software/autoconf-archive/).

This spec is based on sources from [Fedora](https://apps.fedoraproject.org/packages/autoconf-archive/sources/).

## Build steps

* Install dependencies
```
$ sudo yum install rpm-build rpmdevtools
```
* Clone this repository
* Build the RPM:
```
$ cd autoconf-archive-rpm
$ spectool -g -R -C SOURCES autoconf-archive.spec
$ rpmbuild --define "_topdir `pwd`" -bs autoconf-archive.spec
$ rpmbuild --define "_topdir `pwd`" --rebuild SRPMS/autoconf-archive-<version>.src.rpm
```
* The RPM should be written to RPMS/noarch