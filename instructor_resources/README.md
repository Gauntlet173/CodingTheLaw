# Instructor Resources

## Installing Docassemble For Use In This Course

First, you need access to a server that will run Docassemble. I have used Digital Ocean, and their general "droplet" with 2GB of ram is
sufficient for most purposes, and will cost in the range of $40/semester. If you can, get an image with Docker pre-installed.

Once you have a server, log into the server over ssh.

If you did not get an image with Docker pre-installed, install it. You will need to refer to the Docker documentation for instructions on how.

Follow the instructions [here](https://docassemble.org/docs/docker.html#configuration%20options)
for installing Docassemble using Docker. If you do not want to use SSH, only a `DAHOSTNAME` is required in the `env.list` file.

It will take a few minutes for the docker container to download, and for the image to be started. After the image starts running, it will still take
several minutes before you will be able to access the server.

Configure your DNS to point the hostname you are using for your server at the correct address. DNS propogation may require up to a day.

If you are not yet able to access your server by using the assigned hostname, access the server using the server IP address. You will be asked to log in.
Use the username `admin@admin.com` and the password `password` to do so. You will immediately be asked to change the password to something more secure.

## Create Administrator User Account

In the menu in the top right, select "User List" and create a new account for yourself as the instructor by clicking on "Menu" and "Add a User". Under "Privileges" choose "admin."

You can now log out of the admin account (choose "sign out" in the menu on the top right of the page) and log back in using the account you have created for yourself.

## Configure the Docassemble Server

There are a small number of steps that are critical to prepare the server to be able to complete the assignments for the course. For additional configuration options,
including enhanced security features, refer to [this page](https://docassemble.org/docs/config.html) in the Docassemble documentation.

### Configure GitHub Connectivity

The instructions for connecting your Docassemble server to GitHub are located [here](https://docassemble.org/docs/installation.html#github).

Briefly, log into your GitHub account, and in your profile under Developer Settings and OAuth Apps, create a new OAuth app using the callback address
`https://your.server/github_oauth_callback` (use `http` if you are not using SSL).

In your Docassemble server, click on the top right menu and choose "Configuration". Find the entries that look like this:

```
oauth:
...
  github:
    enable: False
    id: asdfasdfasdfasdfasdf
    secret: asdfasdfasdfasdfasdfasdfasdf
```

Take the "Client ID" provided by GitHub and enter it under ID. Take the "Client Secret" provided by GitHub and enter it under secret. Change the eanble value to `True` (use a captial T).

Click Save in the Docassemble configuration screen, and the server will reboot.

### Configure Email Sending

Check the [Docassemble documentation](https://docassemble.org/docs/config.html#mail) for information on how to create and configure an account to be able to send mail from your Docassemble server.



### Other General Configurations
