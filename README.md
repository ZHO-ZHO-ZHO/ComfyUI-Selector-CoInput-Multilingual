# ComfyUI-Selector-CoInput-Multilingual 
## 选择器 + 综合输入模块组 双语版

--------
## Introduction 介绍：
 - ### CoInput 综合输入模组

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

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/cff71549-b188-4405-bfd5-7072d3f79c53)

   * 中英双语：方便更多用户使用
  
     Chinese and English bilingual: convenient for more users

     ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Selector-CoInput-Multilingual/assets/140084057/9cf54af4-6bb2-445e-b607-0ead3f41bcab)
     
   2）版本说明

   分为old和new两种版本(模块命名方式不同以示区别)，大家请根据自己的Comfyui版本选择：

   * old适用于2023.09.08更新之前的Comfyui，模块命名方式为Zho_Nodename

   * New适用于2023.09.08更新之后的Comfyui，模块命名方式为Nodename_Zho

     对比：
     

   2）共包含4种模块

   4 kinds of nodes：
  
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

- ### Selector 选择器

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





















   
