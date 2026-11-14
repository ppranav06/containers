# Use Ubuntu base image
FROM ubuntu:24.04

# Set environment variables to non-interactive (to avoid interactive prompts during installation)
ENV DEBIAN_FRONTEND=noninteractive



# Install necessary dependencies
RUN apt-get update 
RUN apt-get install --fix-missing -y \
    wget \
    libgtk2.0-0 \
    libnss3 \
    libxss1 \
    libasound2 \
    libxtst6 \
    x11-apps \
    dbus-x11 \
    xauth \
    && rm -rf /var/lib/apt/lists/*

# Install Cisco Packet Tracer (replace with the actual path to the .deb file)
COPY cisco-packet-tracer.deb /tmp/cisco-packet-tracer.deb
RUN dpkg -i /tmp/cisco-packet-tracer.deb

# Set the working directory to the location where Packet Tracer is installed
WORKDIR /opt/pt/

# Set display environment variable for GUI
ENV DISPLAY=:0

# Command to run Packet Tracer (adjust the command based on your actual installation)
ENTRYPOINT ["./packettracer"]

# Expose the necessary ports (if any specific ports are required for networking)
EXPOSE 9999

