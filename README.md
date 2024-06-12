Server Deployment:
    1- mkdir teleport && cd teleport
    2- clone from git
    3- edit teleport.yaml file 
    4- place the certificates in certs volume placed in /var/lib/docker/volumes/teleport-certs/_data
    5- docker compose up -d
    Add User:
        1- docker exec -it "container name" tctl users add "username" --roles=access,editor 
        2- access server panel and setting up google authenticator with user

Agent configuration:
    1- install teleport on each agent manually: curl https://goteleport.com/static/install.sh | bash -s 15.4.0
    2- replace /etc/teleport.yaml with teleport-agent.yaml
    3- click on enroll new resource
    4- select desiered platform
    5- copy token from url and replace it in teleport-agent.yaml
    6- restart teleport service (systemctl restart teleport.service)
    7- check connection to server 
    
    
Refrenses:
    Install Teleport: https://goteleport.com/download/
    Adding user roles: https://goteleport.com/docs/management/admin/users/
    