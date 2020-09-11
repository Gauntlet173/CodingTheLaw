# Instructor Resources

## Approach to Teaching Technology

This course is not designed to provide a deep theoretical understanding of computer science, which frees you from needing to adhere to
certain strategies that are good for theoretical understanding, and bad for experiential learning. I have discussed the difficulty of
teaching technology to law students with other instructors of similar courses, and the impression I have been left with is that my
approach with this course has allowed students to go further in their learning than is typical. Here is what I think 
I am doing differently:

* I start with an objective that the students care about. They understand what they will eventually be building, before they learn
  anything about technology.
* I do not teach the students anything they don't need to know in order to achieve the objective directly in front of them.
* I wait for them to need to know something before I explain it.
* I encourage the students to try things before they are confident whether they will work.
* I demonstrate failure, and recovery from failure.

In implementation, what this means is that you must not spend any time explaining, in the abstract, what a "variable" is, or what
Python is, or what YAML is. Teach Docassemble as if it was Microsoft Excel. You click here, you type this, and this neat thing happens.
Teach the deeper understanding parts when they become necessary, and not before. It means trying things live, and seeking out opportunities
to react to error messages.

The real-world experience of coding is 95% software that doesn't work yet. It is unhelpful to hide students from it.

## The Difficulty Teaching Technology to Law Students

In my brief experience, the largest difficulty in teaching technology to law students is communicating how imperitive it is that they ask
for help. Exhorting the students at the start of the semester is insufficient. It is change in the normal expectations that needs to be
nurtured and made as easy as possible. My current approach is to redefine failure as success. Class participation marks are given for
sharing error messages received while working on assignments. I will update this document when I have a better idea whether or not that
works. I am also looking for strategies to reiterate and model, every class, the need to fail visibly.

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
