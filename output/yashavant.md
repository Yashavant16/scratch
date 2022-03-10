# Documenatation Workshop 

### Overview
This is a trial workshop sesion to assist us in understanding the guidelines for writting mosip-related document.

## Types of Documents:

### Type-1

_The paragraph below in describes Admin-Portal_

Using the admin portal,administrator can now retrieve an individuals lost RID or misplaced RID, using the admin portal. the *admin* can now control the levels of location hierarchy they required while creating the registration centers. The level of the hierarchy can be configured through configuration property value.
Using the admin portal, administrator can now map the users to a registration centre and to a zone
Using the admin portal, administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital status etc.Using the admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type-2 

Setting up Registration client

Step1: Download TPM utility and run to get machine keys.
find the instructions to check out, build and run the utility here

Step-2: Whitelist the machine keys in server DB.
Machine name and keys output from utility should be updated in server.

Use the below api to create / whitelist your machine.
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine.

NOTE : 
-> Replace appropriate HOSTNAME in the above curl command.
-> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value.

Step3: Know your userId and required roles
  Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_Supervisor, "Reg_OFFICER"
  
Step-4: Download registration client and start reg-client
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  