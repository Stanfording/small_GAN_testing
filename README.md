# small_GAN_testing
This is a small GAN I built from scratch, so I can learn GAN from ground up. 

### Datasets

The date is CelebHQ but I preprocessed it so that I can load any resolution I want: 16, 64, 128, 512, 1024. The loading process is in the colab notebook.

### Purpose:

It is used for testing different ideas due to its ease in modification and checking result. 

To use it, you will need a google colab account.

Just open the notebook file, click the google colab link and start from there.

So far applied some design of DCGAN, and modified Unrolled GAN.


### My Stablity experience:


First, I tried to make it work in small scale 16 * 16 resolution img generation, learned how to train it stably.
  
  In this process, I learned that 0.00001 learning rate for both D and G can help to train stably. 
  
  I suppose it is because that low learning rate can stop D or G from changing too much that they are almost different functions after training a batch. If I turn both learning rate to 0.0001, then D loss will decrease too fast and G can hardly keep up. DCGAN helped me to know whether I need more capacity. If using DCGAN but have 0.0001 learning rate, it will still be unstable. Once the GAN is stable, applying spectrum Norm to either G or D will cause unwanted effect to the output. So I just stay away from using it.

### Mode collapse

Now I can train gan stably. But it suffer a lot from mode collapse. The W-GAN loss did not help that much but I sticked with it. The Game changer to my mode collapse problem is unrolled GAN. Before using it, I can only see women in the generated output. Just using 10 unrolled step, I can see men in the generated output too. After modifying unrolled GAN to make it more efficient and stable, I can now go 30 and 40 unrolled step. The diversity is improving. But if I improve the unrolled step farther, the quality will suffer. 

### FID LOSS

In another repo, I tried FID LOSS as a side project. It did not work well. But if you are interested, definitely check that out.








