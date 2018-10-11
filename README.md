# LetsencryptApacheContianer
Apache Web Server Container with Letsencrypt free certificate

This is a automated way to bring your own apache container with let's encrypt free certificate. Before we step into the topic please ensure blow package is avaialbe/installed in your system. 

  1. Docker-Ce should be installed. 
  2. Docker-compose should be installed.
  3. It must be Linux system :wink:

# Overview:

Let’s Encrypt is a free, automated, and open certificate authority (CA), run for the public’s benefit. In addition to this, they provide software that can issue the certificates and renew certificates automatically. The software that manages this process is called Certbot, and usually, you would have to install this on your server.

I have used certbot container to generate certificate for our domain. So we need domain name for our server and using with webroot authentication we will vaildate domain verification. 

# Workflow:

This section tells about how the certificates are being generated and applied to our container in a automated way. 

  1. We are creating one temporary web container (apache) for domain validation 
  2. Then we are brining up Certbot contianer to generate the token for domain and validation also.
  3. Once the validation is done certificates will be generated it will be available in local system.
  4. Using the docker volume, we are attaching those certificates to real (prod) apache system.
 
# How to use:

Here is simple way to use script. 

Just do git clone of this repo into local. 

```

git clone https://github.com/iamvijayaragavan/LetsencryptApacheContianer.git .


```

Please ensure there is no service is runnig in 80 & 443.

```

netstat -an  | grep ":80"
netstat -an  | grep ":443"

```

There should be docker and docker-compose must be installed in your system. Check for installation using below command.

```

docker version
docker-compose version

```

That's enough to set go. 

run the shell script (auto.sh) which is available in the repo. 

This auto.sh shell script needs two aruguments. one is domain name for your server and email address for certificate purchase ( Dont bother its free of cost only )

```

bash auto.sh <domain_name> <email_address>  or
sh auto.sh <domain_name> <email_address>
./auto.sh <domain_name> <email_address>

```

This will bing up container with free cose with less in minute.

# Contribution:

Feedback and comments are always welcomes. you can contribute to this project as well. Write mail to success.vijayaragavan@gmail.com
