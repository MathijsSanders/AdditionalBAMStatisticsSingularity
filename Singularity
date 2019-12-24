BootStrap: debootstrap
OSVersion: disco
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%labels
MAINTAINER MathijsSanders

%runscript
exec /bin/bash /code/runScript.sh "$@"

%post
sed -i 's/$/ universe/' /etc/apt/sources.list
apt-get update
apt-get -y install openjdk-12-jre git samtools
cd /tmp/
git clone https://github.com/MathijsSanders/AdditionalBAMStatistics.git
cd AdditionalBAMStatistics/
mkdir /code
mv additionalBamStatistics.jar runScript.sh /code/
chmod u+x /code/runScript.sh
rm -rf /tmp/AdditionalBAMStatistics
apt-get clean

%environment
export LC_ALL=C
