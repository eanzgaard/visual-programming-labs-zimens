установил, проверил, запустил n8n:

PS C:\WINDOWS\system32> docker pull n8nio/n8n
Using default tag: latest
latest: Pulling from n8nio/n8n
3f14a4a8054c: Pull complete
091a19af52d7: Pull complete
7e636500466f: Pull complete
484e0e6f0eae: Pull complete
c6bafa27ed28: Pull complete
4f4fb700ef54: Pull complete
f62e5edcb867: Pull complete
0cbb925e84e3: Pull complete
968b822c8186: Pull complete
4907f4f6eb4a: Pull complete
30aef118d40a: Pull complete
0a79d0617314: Pull complete
f38fdb140cfa: Pull complete
952fd465b865: Pull complete
Digest: sha256:d02752c6ab446ae9db8deec2f9cc887c378f77cdcad31650814df936b7386dfb
Status: Downloaded newer image for n8nio/n8n:latest
docker.io/n8nio/n8n:latest
PS C:\WINDOWS\system32> docker images
                                                                                                    i Info →   U  In Use
IMAGE                     ID             DISK USAGE   CONTENT SIZE   EXTRA
n8nio/n8n:latest          d02752c6ab44       1.82GB          280MB
nodered/node-red:latest   b5adb6c9dd29       1.03GB          235MB    U
PS C:\WINDOWS\system32> docker run -d `
>>   --name n8n-lab `
>>   --restart unless-stopped `
>>   -p 5678:5678 `
>>   -e GENERIC_TIMEZONE=Europe/Minsk `
>>   -e TZ=Europe/Minsk `
>>   -e N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true `
>>   -v "C:\n8n-lab\n8n-data:/home/node/.n8n" `
>>   -v "C:\n8n-lab\data:/data" `
>>   n8nio/n8n
443b94651b9addd0e029c04542964607b0216b70c83cc21cb911194fba942efc
PS C:\WINDOWS\system32> docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                                         NAMES
443b94651b9a   n8nio/n8n   "tini -- /docker-ent…"   50 seconds ago   Up 50 seconds   0.0.0.0:5678->5678/tcp, [::]:5678->5678/tcp   n8n-lab
PS C:\WINDOWS\system32>
