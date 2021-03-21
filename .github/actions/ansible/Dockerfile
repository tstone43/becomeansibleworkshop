FROM centos:centos7.7.1908
RUN yum check-update; \
    yum install -y gcc libffi-devel python3 epel-release; \
    yum install -y openssh-clients; \
    yum install -y git; \
    curl https://packages.microsoft.com/config/rhel/7/prod.repo | tee /etc/yum.repos.d/microsoft.repo; \
    yum install -y powershell; \
    pip3 install --upgrade pip; \
    pip3 install ansible; \
    pip3 install tree; \
    pwsh -c "Set-PackageSource -Name PSGallery -Trusted"; \
    pwsh -c "Install-Module AZ -Scope AllUsers"; \
    pip3 install packaging; \
    pip3 install msrest; \
    pip3 install msrestazure; \
    pip3 install azure; \
    pip3 install ansible[azure]; \
    pip3 install "pywinrm>=0.3.0"

COPY ./entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "bash","entrypoint.sh" ]