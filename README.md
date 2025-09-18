# VM Lifecycle on GCP and OCI — Tutorial

## Video
Loom: <paste link>

## Prereqs
- Cloud access to GCP and OCI
- No PHI/PII; smallest/free-tier shapes

---

## Google Cloud (GCP)
### Create
1. In the Navigation Menu, scroll down and select Compute Engine
2. Select Create Instance
3. Name your Instance
4. Select the Region that is nearest to you
6. Select E2-micro as the Machine type since that is the smallest available, low cost, and used for day-to-day computing
7. In the OS and Storage category, select Ubuntu as the operating system
8. Select the Boot disk as default minimal, which is Balanced Persistent Disk in this case
9. For Network, select the default VPC and ephemeral as the public IP
10. Then click Create Instance

Here is an image of creating an instance with the machine configuration and region:

<img width="1376" height="706" alt="gcp_create" src="https://github.com/user-attachments/assets/cdc9f07a-a277-4ed8-bcb9-decda0eced2e" />


### Start/Stop
1. The instance should now be running
2. To stop the instance, click on the three dots at the end and select Stop

Here is an image on the instance when it was started and then when it was stopped:

<img width="1407" height="716" alt="gcp_running" src="https://github.com/user-attachments/assets/ed2b2f92-d802-4944-b403-d585a59fe4f4" />



### Delete
1. Delete the instance
2. Go to the Overview and verify no disks or snapshots remain by looking at the Resource Footprint

Here is an image of the Cleaned Instance and verification:

<img width="398" height="391" alt="gcp_cleaned" src="https://github.com/user-attachments/assets/3941d2e6-0288-4163-8f66-b9ed591beff2" />



---

## Oracle Cloud (OCI)
### Create
1. In the Navigation Menu, select Compute and then select Instances
2. Select your Compartment and then Create Instance
3. Name your Instance and select the default domain
4. Select Ubuntu as the image
5. Select the Shape as VM.Standard.E2.1.Micro
6. Create a virtual cloud network with a subnet
7. If you are using SSH, allow OCI to generate a key pair and download the private key
8. For the Boot volume choose the default minimal
9. Then continue to create the Instance

This is an image that shows the information to create the Instance such as the domanin, shape, and image:

<img width="1428" height="675" alt="oci_create" src="https://github.com/user-attachments/assets/9f19d2bc-25b9-468e-805a-f18939494887" />

### Start/Stop
1. The Instance should now be running
2. To stop the Instance, click on Actions and then Stop

This image shows the Instance running and then stopping it:

<img width="1155" height="636" alt="oci_running" src="https://github.com/user-attachments/assets/5aec9240-408d-4522-9418-008a64c1fac6" />


### Terminate
1. Click on Actions to Terminate the Instance and delete boot volume
2. Verify cleanup by going to your Resources

This image shows the Instance terminated:

<img width="1075" height="53" alt="oci_cleaned" src="https://github.com/user-attachments/assets/c34bd671-6b30-4754-a19c-9e65148268d2" />

---

## Reflections
### Similarities
- Both follow the same format of creating the virtual machine in terms of first creating an instance, choosing a machine type, confiuring the OS image, and choosing the network
- They follow a similar terminology to run the instance, stop the instance, and terminate it
- They both offer SSH connection

### Differences
- GCP uses terminology such as persistent disks and machines types
- OCI uses terminology such as images and shapes
- GCP has a default virtual private cloud, but OCI has a manual VCN and subnet
- GCP has browser-based SSH, but OCI has public or private SSH keys that you need to generate
  
### Preference (OCI vs GCP) and Why
- I prefer using GCP to create a VM because it is more streamlined and user-friendly. It is a lot faster to create a VM with only a few steps in GCP, while OCI requires more manual steps. GCP does not require you to go through all of the advanced options unless necessary, while OCI does require this. OCI also has a regional capacity that limits some options, but the GCP's free tier is available in many regions. However, OCI does offer a more affordable option, which was around $2 per month, while GCP had an offer of $7.99. 

