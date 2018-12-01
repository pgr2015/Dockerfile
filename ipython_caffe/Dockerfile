FROM bvlc/caffe:gpu
RUN pip install -U pip \
    && pip install -U scikit-learn \
    && pip install -U matplotlib \
    && pip install -U jupyter \
    && pip install -U lmdb \
    && pip install -U python-mnist
# Set the working directory to /caffe
WORKDIR /workspace
VOLUME ["/workspace/data", "/workspace/notebooks"]
# Expose port 8888 (jupyter uses)
EXPOSE 8888
CMD jupyter notebook --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token='2333'
#build image     $ docker build <iamge name> .
#build container $ docker run -d --name ipython_caffe --runtime=nvidia --mount type=bind,source=`pwd`/data,target=/workspace/data --mount type=bind,source=`pwd`/notebooks,target=/workspace/notebooks  -v /tmp/.X11-unix:/tmp/.X11-unix -e GDK_SCALE -e GDK_DPI_SCALE -e DISPLAY=unix$DISPLAY -p 8887:8888 ipython_caffe:gpu
#login ipython http://localhost:8887/ password:2333

