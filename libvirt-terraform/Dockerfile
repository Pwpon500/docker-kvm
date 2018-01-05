FROM pwpon500/alpine-libvirt

RUN apk add --no-cache go git libvirt-dev build-base

RUN wget https://releases.hashicorp.com/terraform/0.11.1/terraform_0.11.1_linux_amd64.zip && unzip terraform_0.11.1_linux_amd64.zip && mv terraform /usr/bin && rm terraform_0.11.1_linux_amd64.zip

RUN GOROOT=/usr/lib/go; export GOROOT && GOPATH=/root/go; export GOPATH && PATH=$PATH:/usr/lib/go/bin:/root/go/bin && mkdir -p /root/go/bin && mkdir -p /root/go/src

RUN mkdir -p /usr/lib/go/src/github.com/dmacvicar && git clone https://github.com/Pwpon500/terraform-provider-libvirt /usr/lib/go/src/github.com/dmacvicar/terraform-provider-libvirt

RUN cd /usr/lib/go/src/github.com/dmacvicar/terraform-provider-libvirt && go install

RUN mkdir -p /root/.terraform.d/plugins && ln -s /usr/lib/go/bin/terraform-provider-libvirt /root/.terraform.d/plugins/terraform-provider-libvirt

