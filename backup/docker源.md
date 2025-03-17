# Docker更换国内镜像源


    sudo mkdir -p /etc/docker
    sudo tee /etc/docker/daemon.json <<-'EOF'
    {
        "registry-mirrors": [
            "https://dockerproxy.com",
            "https://docker.mirrors.ustc.edu.cn",
            "https://docker.nju.edu.cn",
            "https://cr.console.aliyun.com",
            "https://docker.mirrors.ustc.edu.cn",
            "http://hub-mirror.c.163.com",
            "https://hub.daocloud.io",
            "http://mirror.azure.cn",
            "https://mirror.baidubce.com",
            "https://docker.mirrors.sjtug.sjtu.edu.cn",
            "https://docker.nju.edu.cn",
            "https://docker.hpcloud.cloud",
            "https://docker.m.daocloud.io",
            "https://docker.unsee.tech",
            "https://docker.1panel.live",
            "http://mirrors.ustc.edu.cn",
            "https://docker.chenby.cn",
            "http://mirror.azure.cn",
            "https://dockerpull.org",
            "https://dockerhub.icu",
            "https://hub.rat.dev",
            "https://docker.m.daocloud.io",
            "https://dockerproxy.com",
            "https://docker.mirrors.ustc.edu.cn",
            "https://docker.nju.edu.cn",
            "https://cr.console.aliyun.com",
            "https://ccr.ccs.tencentyun.com",
            "https://dockerproxy.com",
            "https://hub-mirror.c.163.com",
            "https://mirror.baidubce.com",
            "https://hubgw.docker.com",
            "https://docker2.luyb.us.kg",
             "https://docker2.luyb2.us.kg"
         ]
    }
    EOF
    sudo systemctl daemon-reload
    sudo systemctl restart docker
