I only use <strong>root</strong><br>


<p>Use with your own risk</p>
<br>
====================================================================
Install docker engine and docker compose plugin first
<br>
#Debian / Ubuntu
<strong>Add docker key:</strong>
<code>apt update
apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc</code>

<strong>Add repo:</strong>
<code>echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null
apt-get update</code>

<strong>Install docker</strong>
<code>apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y</code>

<br><br>

#RHEL / Alma / Rocky / CentOS
<strong>Install necessary tools and add docker repo</strong>
<code>yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo</code>

<strong>Install Docker</strong>
<code>yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin</code>

<strong>Start docker engine</strong>
<code>systemctl enable docker && systemctl start docker</code>

<br><br>

#Fedora
<strong>Install Necessary Tools and add docker repo</strong>
<code>dnf -y install dnf-plugins-core
dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo</code>

<strong>Install Docker</strong>
<code>dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin</code>

<strong>Start docker engine</strong>
<code>systemctl enable docker && systemctl start docker</code>

======================================================================
