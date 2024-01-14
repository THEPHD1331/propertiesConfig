# Steps to Add Aysmmetric encryption-decryption support 

### 1. Run the following command to create a key store with specified filename, alias, store password and key password 

 keytool -genkeypair -alias mytestkey -keyalg RSA -dname "CN=Web Server,OU=Unit,O=Organization,L=City,S=State,C=US" -keypass paras123 -keystore mykeystore -storepass letmein

### 2. Put the generated keystore into resources folder 
### 3. Configure properties for key usage 

encrypt.keystore.location=classpath:key/{keystore-name}.jks

encrypt.keystore.password={password}

encrypt.keystore.alias={alias}

### 4. Run the application and go to Postman to check 
### 5. For Encryption, go to http://localhost:{portNo}/encrypt and send data to be encrpted in POST request. We get encrypted data in response
### 6. For Decryption, go to http://localhost:{portNo}/decrypt and send encrypted data in POST request to get original data in response.

### For more info - [spring-cloud-config-server-ecryption-decryption](https://dev.to/markbdsouza/spring-cloud-config-server-encryption-and-decryption-2ejc)
