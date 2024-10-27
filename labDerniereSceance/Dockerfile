# Use the appropriate base image
FROM ubuntu

RUN apt update
RUN apt install -y python3 
RUN apt install -y  python3-pip
RUN apt install -y curl

RUN pip install  --break-system-packages flask-cors
# Install locales and set French locale


# Create the /app directory
RUN mkdir -p /app

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . /app/  



# Create a non-root user for security reasons
RUN useradd -m apiuser

# Change ownership of the app directory to the new user
RUN chown -R apiuser:apiuser /app

# Switch to the non-root user
USER apiuser

# Expose the Flask default port
EXPOSE 5000

# Command to run Flask
CMD ["python3", "app.py"]
