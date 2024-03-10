# Use the latest Rasa SDK image
FROM rasa/rasa:latest

# Use root user to create directory and install dependencies
USER root

# Copy the current directory into the /app directory in the image
COPY . /app

# Change the ownership of the wait-for-it.sh file to the non-root user
RUN chown 1001:1001 /app/wait-for-it.sh

# Set the working directory
WORKDIR /app

# Install necessary dependencies
RUN pip install python-dotenv rasa-sdk requests

# Expose port 5055
EXPOSE 5055

# Switch back to non-root to run code
USER 1001

# Command to run on container start
CMD ["run", "actions", "--debug"]