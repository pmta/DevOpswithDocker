FROM registry.fedoraproject.org/fedora-minimal:30

ENV user=anaconda
ENV group=anaconda
ENV UID=1234
ENV GID=1234

ENV JUPYTERPORT=8889


# Generic dependencies
RUN touch /etc/dnf/dnf.conf
RUN microdnf -y update && microdnf -y install iproute && microdnf clean all

# Create user and group
RUN groupadd --gid ${GID} ${group} &&  useradd -u ${UID} -g ${GID} -d /home/${user} ${user} && chown -R ${user}:${group} /home/${user}

# Install anaconda
USER ${user}:${group}
WORKDIR /home/${user}
RUN curl -sL https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh -o ./anaconda3_installer.sh && chmod +x ./anaconda3_installer.sh
RUN ./anaconda3_installer.sh -b -p /home/${user}/.bin/anaconda3 && rm -f ./anaconda3_installer.sh

RUN echo "PATH=/home/${user}/.bin/anaconda3/bin:\$PATH" >> /home/${user}/.bashrc

# Additional packages
RUN  yes "" | /home/${user}/.bin/anaconda3/bin/conda install pytorch

CMD source /home/${user}/.bashrc && jupyter-notebook --ip `ip route list scope link | awk '{ print $7 }'` --port=${JUPYTERPORT} --no-browser
EXPOSE ${JUPYTERPORT}

