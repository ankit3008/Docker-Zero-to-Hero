FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy application files
COPY requirements.txt /app
COPY devops /app

# Install Python and dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /venv && \
    /venv/bin/pip install --upgrade pip && \
    /venv/bin/pip install -r requirements.txt

# Expose the port for the application
EXPOSE 8000

# Command to start the application
ENTRYPOINT ["/venv/bin/python"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]




