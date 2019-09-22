# PascalVOC-Training-Retinanet
## Using PascalVOC 2007 Images to Train Retinanet, for beginners

This was my first time training a machine learning model and my first time doing any object detection, so if you too are a beginner, I hope this notebook helps you. I tried to supply explanations and details about the different keras functions being used, and tried to keep the training job as standard as possible for clarity.

I created this jupyter notebook with the goal of training the Retinanet model, by fizyr, which shows great promise in object detection. I used PascalVOC because it was a standard and already annotated dataset, that was in a easy format to use for this training.

I ran this Jupyter Notebook in an AWS EC2 instance. The instance type was a p2.xlarge (which I believe costs around $0.90/hour to run) and I used a Deep Learning AMI Ubuntu.

Each epoch took about 12 hours to run (I believe), and I did use some tmux commands in my AMI terminal to keep jupyter notebook running continously. 
I ran the following lines in my AMI terminal to get tmux going:
- conda install jupyter
- sudo apt-get install -y tmux
- tmux new -s jup
- jupyter notebook --no-browser

Here's some basic controls for tmux
- tmux new -s sessionname = creates new terminal for your jupyter notebook
- ctrl+b d = detach from session without terminating session
- tmux ls = to see sessions
- tmux a # = go to last created session

I could not find a solution to keep the notebook printing its training outputs when I opened up the notebook later in the training job-- it seems that a solution for that issue in Jupyter Notebook doesn't exist yet? So I was only able to see the training's progress by the weights being saved at the end of each epoch (with the epoch # and loss value in the filename).
