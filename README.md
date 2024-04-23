### 一、注册github账户

**1. 进入github的官网**  https://github.com/

**2. 点击右上角注册按钮sign up，来到注册页面**
![image-20240423160704969](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/81beeede-b26b-4acb-a50b-69b134a8f308)

**3. 在光标处输入自己的邮箱，邮箱必须是可以收到邮件的**

![image-20240423160934939](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/1692da17-e0bb-4aa9-b01d-6ce720014599)

**4. 点击Continue，按要求输入密码，继续创建用户名**

**5. 进行相应的验证，点击 create account 后 ，会出现这个界面**

![image-20240423161127721](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/3e7782fb-ce1c-4a2c-a719-e690a015a515)

**6. 这时邮箱就会收到一封邮件，输入邮件中的数字页面会自动跳转**

**7. 到这个界面时，GitHub就创建好了**

![image-20240423161257023](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/2421e4c0-6ad3-49f5-95d1-025413dfb2ea)

**下次登录时，需要点击旁边的sign in，进入登录页面**

![image-20240423161410988](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/bcc766f3-7a63-43e6-ab13-198e29f966ee)

### 二、建立仓库

**1. 点击＋号下的New repository，新建仓库。**

![image-20240423162636038](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/0fcf7212-3773-42b2-9ae9-799215a24020)

2. 添加仓库姓名、仓库描述，根据需要选择Public/Private，以及是否添加README文件。

![image-20240423162407350](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/239c2d5a-f986-4842-a184-647a35eacb9a)

### 三、上传PPT

**1.点击 Add file**

**2.点击Create new file**

![image-20240423164817800](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/05b5b791-ca3f-41f9-a833-0b4e0d5c923c)

3.上传本地的PPT文件。

### 四、学习的计算机技能

​		扩散模型已成为新的最先进的深度生成模型。在图像合成上超越 GAN 之后，扩散模型在众多工作里都显示出了巨大的潜力，例如计算机视觉、自然语言处理、波形信号处理、多模态建模、分子图建模、时间序列建模和对抗性纯化 （adversarial purification）。此外，扩散模型与其他研究领域也有着密切的联系，例如鲁棒学习（robust learning）、代表性学习（representative learning）和强化学习。然而，原始的扩散模型仍然存在采样过程缓慢的问题，通常需要数千个估计steps才能抽取样本。此外，与基于似然的模型（例如自回归模型）相比，它也难以与强劲对手对数似然相比。目前人们已经为解决上述各种局限而做出了许多努力，最近的研究也开始从实际角度来提高扩散模型的性能。

- 横向对比几个比较火的生成模型GAN、VAE、Flow-based Models、Diffusion Models。

- 对于图像生成任务，神经网络的训练数据一般是一些同类型的图片。比如一个绘制人脸的神经网络会用人脸照片来训练。也就是说，神经网络会学习如何把一个向量映射成一张图片，并确保这个图片和训练集的图片是一类图片。而图像生成任务对神经网络来说更加困难一点，缺乏有效的指导。如对于图像分类任务，训练集会给出每一幅图像的类别；对于人脸验证任务，训练集会给出两张人脸照片是不是同一个人；对于目标检测任务，训练集会给出目标的具体位置。然而，图像生成任务是没有标准答案的。图像生成数据集里只有一些同类型图片，却没有指导AI如何画得更好的信息。

	- 神经网络

	![image-20240423192353742](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/4d637c6d-f05b-4080-a423-c0ebd4d33803)

	- GAN:既然不知道一幅图片好不好，就干脆再训练一个神经网络，用于辨别某图片是不是和训练集里的图片长得一样。生成图像的神经网络叫做生成器，鉴定图像的神经网络叫做判别器。两个网络互相对抗，共同进步。

	![image-20240423192439996](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/9cdcf6e9-4956-4102-b88a-5c17b21e58d1)

	- VAE：用向量生成图像很困难，那就同时学习怎么用图像生成向量。这样，把某图像变成向量，再用该向量生成图像，就应该得到一幅和原图像一模一样的图像。每一个向量的绘画结果有了一个标准答案，可以用一般的优化方法来指导网络的训练了。VAE中，把图像变成向量的网络叫做编码器，把向量转换回图像的网络叫做解码器。其中，解码器就是负责生成图像的模型。

	![image-20240423192551349](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/4bbb83ef-ae80-4f65-86b4-c7dcb9d10fe3)

	- Diffusion：扩散模型由**正向过程**和**反向过程**这两部分组成，对应VAE中的编码和解码。正向过程中，不断混入高斯噪声，经过T次操作后，图像会变成一幅符合标准正态分布的纯噪声图像；在反向过程中，训练出一个去除T次噪声的网络，把图像还原，但是本质是新图像。

	![image-20240423192951347](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/2a2dd7f1-0f13-4a6c-88a6-332f7916b8c6)

	正向过程：![image-20240423193158255](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/a3e3be38-a8a9-47ba-b383-621732c6f517)
反向过程：

	![image-20240423193237584](https://github.com/smallder123/WuWenlianDataMing/assets/152846176/e1a2c237-b3b9-4d75-a8e1-610af17f6253)

	尽管扩散模型目前取得了很好的生成效果，到其逐步去噪的过程涉及非常多的迭代步骤，故此扩散模型的加速是很重要的研究课题。

