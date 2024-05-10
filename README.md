I only use <strong>root</strong><br>


<p>Use with your own risk</p>
<br>
====================================================================
<br>
Install docker engine and docker compose plugin first:
<br>
<strong>Debian / Ubuntu</strong>
#Add docker key:
<code>apt update
apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc</code>

#Add repo:
<code>echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null
apt-get update</code>

#Install docker
<code>apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y</code>

<br><br>

<strong>RHEL / Alma / Rocky / CentOS</strong>
#Install necessary tools and add docker repo
<code>yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo</code>

#Install Docker
<code>yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin</code>

#Start docker engine
<code>systemctl enable docker && systemctl start docker</code>

<br><br>

<strong>Fedora</strong>
#Install Necessary Tools and add docker repo
<code>dnf -y install dnf-plugins-core
dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo</code>

#Install Docker
<code>dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin</code>

#Start docker engine
<code>systemctl enable docker && systemctl start docker</code>

======================================================================
