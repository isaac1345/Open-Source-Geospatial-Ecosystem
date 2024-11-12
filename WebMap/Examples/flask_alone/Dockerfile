FROM python:3.11

# Set up environment variables for Python
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Copy only the requirements file first to leverage Docker caching
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# add app folder contents to WORKDIR
COPY app ./app

# Expose the port your application will run on
EXPOSE 5000

# Specify the command to run on container start
WORKDIR /app
CMD [ "python3", "-m" , "flask", "--app", "app/app", "run"]