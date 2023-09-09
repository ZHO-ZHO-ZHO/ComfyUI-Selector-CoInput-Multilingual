# ComfyUI-Selector-CoInput-Multilingual 
## 选择器 + 综合输入模块组 双语版

--------
## Introduction 介绍：
  ### 1. CoInput 综合输入模组

   1）设计目的
   
   Design Purpose

   * 高效整合：整合了各种单独模块，适用于任何工作流，尤其便于搭建大型工作流，可以有效的将工作流简化
  
     Efficient Integration: It integrates various standalone nodes, suitable for any workflow, especially for constructing large workflows, effectively simplifying the workflow.

   * 利于复用：大型工作流往往需要很多统一的输入项，原始节点只能以单独的形式出现，导致界面十分混乱（参数零散、输入输出相分离）不利于使用

     Facilitates Reusability: Large workflows often require many standardized input items. Original nodes can only appear in separate forms, resulting in a cluttered interface (with scattered parameters and separated input/output), which is not user-friendly.

   * 简化界面：将输入项统一，同时将输入输出与运行相分离，界面更直观
  
     Streamlined Interface: Standardizing input items while separating input/output from execution makes the interface more intuitive.

   * 直观对比：整合之后与原始工作流的对比

     Visual Comparison: A comparison between the integrated workflow and the original workflow.

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/a8927f9d-e8e8-44f3-b5ea-ae5ae28e5a4f)

   * 中英双语：方便更多用户使用
  
     Chinese and English bilingual: convenient for more users

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/9cf54af4-6bb2-445e-b607-0ead3f41bcab)

   * 与[efficiency-nodes-comfyui](https://github.com/LucianoCirino/efficiency-nodes-comfyui/tree/main)区别

     Differences from efficiency-nodes-comfyui:：

     efficiency-nodes（直接把所有加载器整合到了一起）的缺点是只要有一项参数修改，所有内容都会被再次加载一遍（尤其是主模型会被重复加载），运行速度被极大的降低。

     The drawback of efficiency-nodes (which directly integrates all loaders) is that whenever any parameter is modified, everything is reloaded (especially the main model is reloaded), significantly slowing down the execution speed.     

     Co_Input_Zho（综合输入器）只是把所有的参数数值整合到了一起，并未与加载器合并，修改参数不会导致重复加载，解决了运行速度降低的问题。Co_Loader（模型加载器）和Parameter_Loader（参数加载器）都分别做了整合：模型加载器对主模型、CLIP跳过层、VAE模型、LoRA模型进行了整合，参数加载器对正负提示词和初始潜空间进行了整合。

     Co_Input_Zho simply consolidates all parameter values without merging them with loaders. Modifying parameters does not lead to redundant reloading, resolving the issue of reduced execution speed. Co_Loader (Model Loader) and Parameter_Loader (Parameter Loader) are both integrated separately: the model loader consolidates the main model, CLIP skip layers, VAE models, and LoRA models, while the parameter loader consolidates positive and negative prompts and the empty latent space.

   2）版本说明
   
   Version Information:
   
   * 分为old和new两种版本(模块命名方式不同以示区别)，大家请根据自己的ComfyUI版本选择：
  
     Divided into two versions, old and new (with different module naming conventions for distinction). Please choose according to your ComfyUI version:

       * old适用于2023.09.08更新之前的ComfyUI，模块命名方式为Zho_Nodename
    
         Old version is suitable for Comfyui versions before the update on September 8, 2023, with module naming in the format Zho_Nodename.

       * New适用于2023.09.08更新之后的ComfyUI，模块命名方式为Nodename_Zho
    
         New version is suitable for Comfyui versions updated on or after September 8, 2023, with module naming in the format Nodename_Zho.

     对比 | Comparison:
     

   3）4种模块的说明

   Introduction of the 4 nodes:
  
   - 综合输入器_Zho | Co_Input_Zho
     
     功能：输入Clip跳过层(数值)、宽度、高度、交换宽高、生成数量、正负提示词（文本）、种子、步数、CFG、降噪值
     
     Function：Input clip_skip(INT), width, height, swap_width_height, batch_size, positive(str), negative(str), seed, steps, cfg, denoise

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/feb60c49-c19e-4fe6-ab82-5a4b7294ee82)

  
   - 模型加载器_Zho | Co_Loader_Zho
  
     功能：加载主模型、CLIP跳过层、VAE模型、LoRA模型（设定强度）
     
     Function：Load main model, CLIP skip layers, VAE models, and LoRA models(set strength)

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/ae392900-59e7-4660-b672-7e1bbf3f7c22)

  
   - 参数加载器_Zho | Parameter_Loader_Zho
  
     功能：编码正负提示词、加载初始潜空间
     
     Function：Encode positive and negative prompts and the generate empty latent space

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/477a296a-496b-4dfe-90f5-c514d0aec36f)

  
   - 初始潜空间_交换_Zho | EmptyLatent_Swap_Zho
  
     改变：在原始的加载初始潜空间模块航增加了交换宽度与高度的按钮
     
     Change: A button for swapping width and height has been added to the original load empty latent space node.

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/c4cc8402-03c1-47cc-b408-369549753102)

   4）模块分类

   Category：

   ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/106ba7a0-9040-4ae6-b60d-2d9495bd8d12)

   5）如何使用

   How to use：

   * 模型加载器 + 参数加载器 | Co_Loader_Zho + Parameter_Loader_Zho
     
     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/bd1d88b9-897a-446d-99f6-818a9e39650e)

   * 综合输入器 + 模型加载器 + 参数加载器 | Co_Input_Zho + Co_Loader_Zho + Parameter_Loader_Zho
     
     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/9a439214-63ed-4a96-8731-e8457700a278)


   6）使用示例（结合Selector选择器使用）
   
   Example(Combined with Selector)：
   
   ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/71278e12-bb49-42cd-9e5a-f5f3baf36bab)

   * 工作流说明
     
       * 2种模型（主模型、VAE、LoaRA）输入选择
         
       * 3种VAE输入选择
         
       * 3种潜空间输入选择
         
           - 初始潜空间（文生图）
             
           - 图片编码为潜空间（图生图）
             
           - Plasma噪点图编码为潜空间-文生图）
             
       * 10种提示词输入选择
         
       * 3种条件输入选择
       * 
           * 文生图
             
           * CtrlNet-Canny（包含10种预处理器可选择）
             
           * CtrlNet-Depth（包含4种预处理器可选择）


   * Workflow Explanation:

       * Selection of 2 models (main model, VAE, LoaRA)

       * Selection of 3 VAE inputs

       * Selection of 3 latent space inputs

           - Initial latent space (Text-to-Image)

           - Image encoded to latent space (Image-to-Image)

           - Plasma noise map encoded to latent space (Text-to-Image)

       * Selection of 10 prompt inputs

       * Selection of 3 conditioning inputs

           * Text-to-Image

           * CtrlNet-Canny (including 10 selectable preprocessors)

           * CtrlNet-Depth (including 4 selectable preprocessors)


--------

 ### 2 Selector 选择器

   1）设计目的：方便选择各种不同的输入，可用于搭建大型专业工作流

   Design Purpose: To facilitate the selection of various inputs, suitable for constructing large-scale professional workflows.

   2）共包含9种选择器

   9 kinds of selectors：
  
   - Model
  
   - LoRA
  
   - CLIP
  
   - VAE
  
   - Text
  
   - Image
  
   - Latent
  
   - Conditioning_Input
  
   - Ctrlnet

   3）每种选择器提供9个选项（1-9），并且支持多个选择器串联（以满足更多选择需求）

   Each selector provides 9 options (1-9), and multiple selectors are supported in series (to meet more selection needs)

   4）特别注意：所有选择器前2个输入为必选项，后7个输入为可选项（即至少需要输入两个选项）

   Note: The first 2 inputs of all selectors are required and the last 7 inputs are optional (i.e., at least two options are required)

   5）模块图示

   Looks Like：

  ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/fbc96d73-81bd-4261-acb0-98be3df9f38e)

   6）模块分类

   Category：
  
  ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/6dac0403-19ba-4bae-ac29-c9fd302c5d28)

   7）使用示例：紫色表示各种不同的选择器，用于选择多种不同的输入

   Example：Purple nodes represent various selectors used to choose multiple different inputs.

  ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/fef96c9e-74a3-4b8c-b831-f90418bc21bb)


--------
使用CoInput_Zho与否的对比 | Comparison of Using CoInput_Zho and Not Using It:

未使用 | Without Using:

  ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/fef96c9e-74a3-4b8c-b831-f90418bc21bb)

使用 | Using:：

   ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/71278e12-bb49-42cd-9e5a-f5f3baf36bab)

--------
### Install 安装:

- CoInput 综合输入模块组
  
   1）首先根据自己ComfyUI版本选择下载old或new（ComfyUI版本在2023.09.08之前的选择old）
  
  First, choose to download either old or new based on your ComfyUI version(Choose "old" for ComfyUI versions before September 8, 2023）.
  
   2）下载好之后解压放置到custom nodes文件夹（注意解压之后不要有嵌套）
  
  After downloading, extract and place it in the custom node folder (make sure there are no nested folders after extraction).

   3）重启ComfyUI
  
  Restart ComfyUI.


- Selector 选择器模块组
  
   1）下载好之后解压放置到custom nodes文件夹（注意解压之后不要有嵌套）
  
  After downloading, extract and place it in the custom node folder (ensure there are no nested folders after extraction).

   2）重启ComfyUI
  
  Restart ComfyUI.













   
