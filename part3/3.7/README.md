# 3.7(b)

Docker is readily available on (nearly) any operating system. It typically requires no manual setup by user or really even much knowledge on how the Docker works under the hood. This makes it easy also for beginners to start experimenting with available existing container images. The containers have all needed executables and libraries they need so user don’t need install bunch of pre-requirements to run the application.

For example say you are developing web application and you are using Ruby on Rails. Some gems have requirements such as SQLite or PostgreSQL. What happens when your target machine has already PostgreSQL installed for some legacy application but it is a wrong version? You might be able to upgrade it (assuming you can bring the legacy service down for maintenance) but you might be risking breaking the existing legacy application. 
Or alternatively you might be able to install the version Ruby on Rails wants in parallel with existing installation. This is already risky as you need the take care that the versions don’t interfere. Have different version on the same system and you risk accidentally using the wrong one depending how your environment variables, library search paths etc. are set up. 
Even if you are able setup everything correctly, what happens when you need to upgrade the server hardware? Do it all again on newly installed system?

If you do run your Ruby on Rails application in Docker container, you can have all the requirements in isolated environment without fear of interfering with any existing on future applications. 
Need to setup the application on a new server? You can easily replicate the setup with Docker container on the new server with the correct dependencies deployed. No need to figure out if the operating system on the new server has compatible versions available. 



