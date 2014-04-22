php54: stable 5.4.27, HEAD
http://php.net
/usr/local/Cellar/php54/5.4.24 (488 files, 37M)
  Built from source
/usr/local/Cellar/php54/5.4.25 (488 files, 37M)
  Built from source
/usr/local/Cellar/php54/5.4.26 (488 files, 37M)
  Built from source
/usr/local/Cellar/php54/5.4.27 (488 files, 37M) *
  Built from source
From: https://github.com/josegonzalez/homebrew-php/commits/master/Formula/php54.rb
==> Dependencies
Required: freetype ✔, gettext ✔, jpeg ✔, libpng ✔, unixodbc ✔, homebrew/dupes/zlib ✔
Optional: gmp ✔
==> Options
--homebrew-apxs
	Build against apxs in Homebrew prefix
--with-apache
	Enable building of shared Apache 2.0 Handler module, overriding any options which disable apache
--with-cgi
	Enable building of the CGI executable (implies --without-apache)
--with-debug
	Compile with debugging symbols
--with-fpm
	Enable building of the fpm SAPI executable (implies --without-apache)
--with-gmp
	Build with gmp support
--with-homebrew-curl
	Include Curl support via Homebrew
--with-homebrew-libxslt
	Include LibXSLT support via Homebrew
--with-homebrew-openssl
	Include OpenSSL support via Homebrew
--with-imap
	Include IMAP extension
--with-intl
	Include internationalization support
--with-libmysql
	Include (old-style) libmysql support
--with-mssql
	Include MSSQL-DB support
--with-pdo-oci
	Include Oracle databases (requries ORACLE_HOME be set)
--with-pgsql
	Include PostgreSQL support
--with-phpdbg
	Enable building of the phpdbg SAPI executable (PHP 5.4 and above)
--with-thread-safety
	Build with thread safety
--with-tidy
	Include Tidy support
--without-apache
	Build without shared Apache 2.0 Handler module
--without-bz2
	Build without bz2 support
--without-mysql
	Remove MySQL/MariaDB support
--without-pcntl
	Build without Process Control support
--without-pear
	Build without PEAR
--HEAD
	install HEAD version
==> Caveats
The php.ini file can be found in:
    /usr/local/etc/php/5.4/php.ini

✩✩✩✩ PEAR ✩✩✩✩

If PEAR complains about permissions, 'fix' the default PEAR permissions and config:
    chmod -R ug+w /usr/local/Cellar/php54/5.4.27/lib/php
    pear config-set php_ini /usr/local/etc/php/5.4/php.ini

✩✩✩✩ Extensions ✩✩✩✩

If you are having issues with custom extension compiling, ensure that
you are using the brew version, by placing /usr/local/bin before /usr/sbin in your PATH:

      PATH="/usr/local/bin:$PATH"

PHP54 Extensions will always be compiled against this PHP. Please install them
using --without-homebrew-php to enable compiling against system PHP.

✩✩✩✩ PHP CLI ✩✩✩✩

If you wish to swap the PHP you use on the command line, you should add the following to ~/.bashrc,
~/.zshrc, ~/.profile or your shell's equivalent configuration file:

      export PATH="$(brew --prefix homebrew/php/php54)/bin:$PATH"

To have launchd start php54 at login:
    ln -sfv /usr/local/opt/php54/*.plist ~/Library/LaunchAgents
Then to load php54 now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.php54.plist
