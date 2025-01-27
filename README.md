# Listeem-app

Welcome to Listeem development page ! 🚀 

If you don't know what Listeem is, please first visit [this link](https://github.com/Pozinux/listeem) to learn more about it. 

If you just want to install the latest version of Listeem and use it for yourself on your own server or computer, Listeem is provided in the form of a Docker container publicly stored on Docker Hub. Please follow the installation steps described at [this link](https://github.com/Pozinux/listeem)

However, if you want to contribute to this project, you are at the right place!

## Installation of development version

To get started, follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Pozinux/listeem-app.git
    ```

2. **Navigate to the project directory:**
 
    ```bash
    cd listeem-app
    ```

3. **Create your configuration:**
    
    Copy the `env_template` file to a `.env` file.
    
    Modify the `.env` file with your settings following instructions commented in the file.

    Example :

    ```bash
    PROJECT_ID=3
    COMPOSE_PROJECT_NAME=listeem_${PROJECT_ID}
    MYSQL_USER=user1
    MYSQL_PASSWORD=pass1
    MYSQL_ROOT_PASSWORD=rootpassword
    MYSQL_DATABASE=listeem_container_db
    KEY_TO_ENCRYPT_DECRYPT_DB=fds54dfg654897sdf312sdf3
    HTTP_PORT=8077
    HTTPS_PORT=8078
    SERVER_NAME=example.com
    #SSL_CERT_FILE=/etc/apache2/ssl/fullchain.pem
    #SSL_KEY_FILE=/etc/apache2/ssl/privkey.pem
    ```

4. **(Optional) Add your own SSL certificate for HTTPS:**
    
    Create a folder named `ssl` and add your `privkey.pem` and `fullchain.pem` files to this folder. They have to be named exactly this way.

At this step, you should have the following directories and files:

![screen2](https://github.com/Pozinux/listeem-app/assets/8541705/03b5b266-9e48-4702-ae80-6fdb5c4c24e6)


5. **Run the application:**
   
    ```bash
    docker compose up -d
    ```

Now, the Listeem application should be up and running. 

To view it in HTTP, open your web browser and visit:

`http://your-server-domain:8077`

To view it in HTTPS (with the self signed certificate or your own certificate), open your web browser and visit:

 `https://your-server-domain:8078`

## Contributing

If you want to contribute to the code, don't hesitate to open a pull request. Thanks!

## Possible errors

**Case 1**

 ```bash
BDD connection error : Connection refused
 ```

or 

 ```bash
Fatal error: Uncaught Error: Call to a member function execute()
 ```

Three possible reasons to this error:

1. The database is still initializing
3. It is a browser cache issue
4. The server runs out of memory
   
Wait a few seconds, visit another web page and come back.

**Case 2**

 ```bash
Bad Request
 ```

You are probably trying to open the url on HTTPS port (probably 8078). Add 'https://' in front of your url or change port to HTTP port (probably 8077).
