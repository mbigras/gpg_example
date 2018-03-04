Hack session using gpg

mkdir somedir
ed somedir/somefile
tar czf files.tar.gz somedir
echo some super secret | lpass add --sync now --non-interactive --notes gpg-example
lpass show --notes gpg-example | gpg --batch --passphrase-fd 0 -c files.tar.gz
rm files.tar.gz
lpass show --notes gpg-example | gpg --batch --passphrase-fd 0 files.tar.gz.gpg
tar xzf files.tar.gz
cat somedir/somefile
hello world!

Links

https://stackoverflow.com/questions/19895122/how-to-use-gnupgs-passphrase-fd-argument