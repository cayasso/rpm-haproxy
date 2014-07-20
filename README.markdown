# A Recipe for a haproxy 1.5 stable version RPM on CentOS

Perform the following on a build box as a regular user.

## Create an RPM Build Environment

Install rpmdevtools from the [EPEL][epel] repository:

```bash
$ sudo yum install rpmdevtools pcre-devel
$ rpmdev-setuptree
```

## Install Prerequisites for RPM Creation

```bash
$ sudo yum groupinstall 'Development Tools'
$ sudo yum install openssl-devel
```

## Build the RPM file

```bash
$ make build
```

The resulting RPM will be the `rpmbuild/i686` directory in your git `rpm-haproxy` folder.

Files created should look something similar to this:

```bash
$ ls
haproxy-1.5.2-11.amzn1.i686.rpm
haproxy-debuginfo-1.5.2-11.amzn1.i686.rpm
```

## Credits

Based on the Red Hat 6.4 RPM spec for haproxy 1.4.

Maintained by [Martijn Storck](martijn@bluerail.nl)

[EPEL]: http://fedoraproject.org/wiki/EPEL#How_can_I_use_these_extra_packages.3F
