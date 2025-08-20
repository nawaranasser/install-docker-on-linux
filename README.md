# install-docker-on-linux os
--------------------------------------

## •	Remove any dependences if any 
sudo dnf remove docker \ 
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine \
                  podman \
                  runc
 <img width="842" height="601" alt="image" src="https://github.com/user-attachments/assets/acaee7a6-1c0e-4aa2-b528-ebabfd5bb954" />


## •	Remove the Existing Docker Repository if any
sudo rm -rf  /etc/yum.repos.d/docker-ce.repo
 
 <img width="940" height="116" alt="image" src="https://github.com/user-attachments/assets/02b868c0-4794-48e3-9c97-b3254bd549f6" />


<img width="940" height="123" alt="image" src="https://github.com/user-attachments/assets/41153259-320e-45e2-919f-10220927d104" />


## •	Install yum 
yum install -y yum-utils
 
## •	Add a New Docker Repository
yum config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo 

<img width="940" height="76" alt="image" src="https://github.com/user-attachments/assets/1de683ab-73db-4a97-b34d-e65331d22c57" />


## •	Ensure the repo was added
ls -l /etc/yum.repos.d/

<img width="636" height="50" alt="image" src="https://github.com/user-attachments/assets/35bf6e50-c165-4dd4-9f81-7e5a89283645" />
 

## •	Install docker 
sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

<img width="940" height="567" alt="image" src="https://github.com/user-attachments/assets/63b98ad5-cc42-46a3-9483-0160fa826418" />
 

## •	Docker still disables
Service docker status

<img width="940" height="156" alt="image" src="https://github.com/user-attachments/assets/ef8c0916-1c75-457a-9a55-5e0503b1b448" />

 
## •	Enable docker
systemctl enable --now docker

 <img width="940" height="52" alt="image" src="https://github.com/user-attachments/assets/68db6b76-4cda-4756-9625-c12353053ec5" />

## ensure it is enabled

 <img width="940" height="261" alt="image" src="https://github.com/user-attachments/assets/26b1423e-348e-4bc5-ae6d-4daa9327922b" />

Or 

 <img width="940" height="260" alt="image" src="https://github.com/user-attachments/assets/b77ab927-63fc-408b-9bc8-e9623efe5b9d" />


## •	Run the first docker img
docker run hello-world

 <img width="1078" height="508" alt="image" src="https://github.com/user-attachments/assets/269adc8b-5989-4123-9621-c655d29f7922" />


# •	It is running correctly now on root user only 
# •	If switch to any regular user , permission denied is appeared 
 
<img width="940" height="125" alt="image" src="https://github.com/user-attachments/assets/d506342f-ec90-4e48-8450-e90d1c8ed384" />


## •	Allow nora user to use docker by join to docker group
usermod -aG docker nora
 
  <img width="631" height="42" alt="image" src="https://github.com/user-attachments/assets/534f8097-922f-4b8d-b6a9-5d0fe795d30f" />

### to ensure this step

<img width="611" height="98" alt="image" src="https://github.com/user-attachments/assets/29f6dff7-7150-425d-9f0d-856861104745" />

  
## •	Now nora user can use docker 

<img width="940" height="109" alt="image" src="https://github.com/user-attachments/assets/41d66401-184d-4955-818e-ddd0ca09bc92" />




