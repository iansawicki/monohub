# Use the official Jupyter base image as a base
FROM jupyter/minimal-notebook:latest

# Copy notebooks
COPY nbs /home/jovyan/

# Copy images
COPY /home/isawicki/Developer/images /home/jovyan/images

# Append the Spawner arguments to the Jupyter config file
RUN echo "c.NotebookApp.allow_origin = '*'" >> /home/jovyan/.jupyter/jupyter_notebook_config.py

