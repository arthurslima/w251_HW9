# Homework 9: Distributed Training and Neural Machine Translation

## How long does it take to complete the training run? (hint: this session is on distributed training, so it will take a while)
  It took 1h 53min to complete te training run
## Do you think your model is fully trained? How can you tell?
  No. The model checkpoint is generated every 4k interactions.
## Were you overfitting?
  No. If we were overfitting, we would see that the accuracy of our model on the validation data would peak after training for a number of epochs, and would then start decreasing
## Were your GPUs fully utilized?
  Yes. When running the nvidia-smi command, we can see that the GPUs are at 100% Util (see image attached here named CPU.jpeg)
## Did you monitor network traffic (hint: apt install nmon ) ? Was network the bottleneck?
  Yes, I monitored. It was not a bottleneck.
## Take a look at the plot of the learning rate and then check the config file. Can you explan this setting?
  The learning rate decreases with the incrementality of the BLEU score.
## How big was your training set (mb)? How many training lines did it contain?
  To train we used the file: train.clean.en.shuffled.BPE_common.32K.tok<br>
  It has 958.6MB <br>
  It has 4524868 lines
## What are the files that a TF checkpoint is comprised of?
  val_loss=1.5943-step-44012.data-00000-of-00001 .  --  Model<br>
  val_loss=1.5943-step-44012.index .  --- Index<br>
  val_loss=1.5943-step-44012.meta .  --- Meta<br>
## How big is your resulting model checkpoint (mb)?
  it is 852.3MB
## Remember the definition of a "step". How long did an average step take?
  In tensorflow one steps is considered as number of epochs multiplied by examples divided by batch size.<br>
  The average step took 0.59 seconds
## How does that correlate with the observed network utilization between nodes?
  The step duration is directly proporcional to the network utilization between nodes. <br>
  The higher the utilization, higher will be the time to run the step.
