FROM python:3.7
# Update and upgrade system packages
RUN apt-get update -y && apt-get upgrade -y

# Install required system dependencies
RUN apt-get install \
    gcc nano \
    ffmpeg libasound-dev portaudio19-dev libportaudio2 libportaudiocpp0 \
    postgresql postgresql-contrib -y

# Install Python packages
RUN pip install numpy scipy matplotlib pydub pyaudio psycopg2 jupyter

# Set the working directory inside the container
WORKDIR /code

# Expose the port for Jupyter Notebook
EXPOSE 8888

# Run Jupyter when the container starts
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--NotebookApp.token='abcd1234'","--NotebookApp.password='abcd1234'"]
