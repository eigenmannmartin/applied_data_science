FROM jupyter/minimal-notebook

# Switch to root user
USER root

# Create a new user
ENV HOME /home/user
RUN useradd --create-home --home-dir $HOME user \
    && chmod -R u+rwx $HOME \
    && chown -R user:user $HOME

# Install additional Python libraries
RUN pip install \ 
		matplotlib \ 
		pandas \ 
		numpy \
		seaborn \
		openpyxl \
		requests \
		Pyarrow

# Switch to user
WORKDIR $HOME
USER user

# Add Jupyter notebook and data
ADD apartments_data_kt_zuerich.ipynb /home/user/
ADD apartments_data_prepared.csv /home/user/