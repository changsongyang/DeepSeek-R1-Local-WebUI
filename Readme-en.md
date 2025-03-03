# DeepSeek-R1-Local-WebUI

<div style="text-align:center">
  <a href="Readme.md">简体中文</a> | <a href="Readme-en.md">English</a>
</div>

---

**DeepSeek-R1-Local-WebUI** is a Flask-based local model deployment project launched via a CLI console. It provides an interactive web interface for conversing with the [DeepSeek-R1](https://github.com/deepseek-ai/DeepSeek-R1) model. The project supports streaming response generation and offers Light/Dark theme switching.

---

## Project Functionality

- **CLI Console**: Manage the project through a command-line interface.
- **Local Model Deployment:** Uses Hugging Face's transformers library to load and run the [DeepSeek-R1](https://github.com/deepseek-ai/DeepSeek-R1) model.
- **Web Interface:** Provides Web services through Flask, allowing users to converse with the model in their browser.
- **Theme Switching:** Supports switching between Light and Dark themes to enhance user experience.
- **Model Selection:** Offers multiple models for users to choose from, catering to different hardware configurations.

---

## Project Structure

```
DeepSeek-R1-Local-WebUI                 
├─ config                   # Configurations                   
│  ├─ generation.py                      
│  ├─ webui.py                           
│  └─ __init__.py                        
├─ core                     # Core Code                   
│  ├─ generator.py                       
│  ├─ model_manager.py                   
│  └─ __init__.py                                                
├─ scripts                  # Core Scripts            
│  ├─ memory_monitor.py                  
│  └─ model_downloader.py                
├─ static                   # Static Resources            
│  ├─ css                                
│  │  └─ app.d8079a91.css                
│  └─ js                                 
│     ├─ about.ddee9fe6.js               
│     ├─ about.ddee9fe6.js.map           
│     ├─ app.20cd43bb.js                 
│     ├─ app.20cd43bb.js.map             
│     ├─ chunk-vendors.28b75eeb.js       
│     └─ chunk-vendors.28b75eeb.js.map   
├─ templates                # Template Files                
│  └─ index.html                         
├─ web                      # Main Program                   
│  ├─ routes.py                          
│  ├─ utils.py                           
├─ DeepSeek-R1_LICENSE      # DeepSeek-R1 License File
├─ install_dependencies.py  # Dependency Installation Script
├─ LICENSE                  # License File
├─ Readme-en.md             
├─ Readme.md                
├─ requirements.txt         # Dependency Files
└─ cli.py                   # CLI Startup Script
```

---

## Installation and Running

### Preparation before Installation

Visit [NVIDIA CUDA Toolkit 12.1 Downloads](https://developer.nvidia.com/cuda-12-1-0-download-archive) to download and install the CUDA Toolkit 12.1 according to your system requirements.

### Windows

#### install manually

1. Clone the project
```bash
git clone https://github.com/WavesMan/DeepSeek-R1-Local-WebUI.git
cd DeepSeek-R1-Local-WebUI
```

2. Install dependencies
 ```bash
py -m venv deepseek_env              # Create virtual environment
.\deepseek_env\Scripts\activate      # Activate environment
pip install -r cli-require.txt       # Install dependencies
```

3. Run the CLI:
```bash
python cli.py                        # Start CLI
```

4. Access WebUI
Visit `http://127.0.0.1:5000` to use the WebUI.

### Linux/Mac

1. Clone the project
```sh
git clone https://github.com/WavesMan/DeepSeek-R1-Local-WebUI.git
cd DeepSeek-R1-Local-WebUI
```

2. Install dependencies
 ```bash
py -m venv deepseek_env              # Create virtual environment
.\deepseek_env\Scripts\activate      # Activate environment
pip install -r cli-require.txt       # Install dependencies
```

3. Run the CLI:
```bash
python cli.py                        # Start CLI
```

4. Access WebUI
Visit `http://127.0.0.1:5000` to use the WebUI.

---

## Dependencies

- **Python 3.11+**: The project is developed using Python 3.11; significant errors may occur with Python 3.9 and below. **It is recommended to use Python 3.11**.
- **Flask**: Used for providing Web services.
- **Transformers**: Used for loading and running the DeepSeek-R1 model.
- **Torch**: Used as the deep learning framework for model inference.
- **FontAwesome**: Used for interface icons.

---

## Notes

- **Model Download:** The first time running the program requires downloading the DeepSeek-R1 model, which is quite large. Ensure a stable internet connection.
- **GPU Requirements:** Model inference requires a certain amount of GPU VRAM; it is recommended to use a GPU that supports CUDA.
- **Streaming Generation:** Streaming generation functionality is currently unavailable; it will be supported in future versions.

---

## Model Selection
| Model Name | Number of Parameters | VRAM Requirements | Recommended Graphics Card (Minimum) |
| --- | --- | --- | --- |
| DeepSeek-R1-Distill-Qwen-1.5B | 1.5B | 4-6 GB | GTX 1660 Ti, RTX 2060 |
| DeepSeek-R1-Distill-Qwen-7B | 7B | 12-16 GB | RTX 3060, RTX 3080 |
| DeepSeek-R1-Distill-Llama-8B | 8B | 16-20 GB | RTX 3080 Ti, RTX 3090 |
| DeepSeek-R1-Distill-Qwen-14B | 14B | 24-32 GB | RTX 3090, RTX 4090 |
| DeepSeek-R1-Distill-Qwen-32B | 32B | 48-64 GB | A100, H100 |
| DeepSeek-R1-Distill-Llama-70B | 70B | 80-128 GB | A100, H100, MI250X |

---

## Changelog

### v1.0.0 (Initial Release)

- **Features:**
  - Support for local deployment of the DeepSeek-R1 model.
  - Provide a Web interface for user interaction with the model through the browser.
  - Support for Light/Dark theme switching.
  - Multiple models available for selection, adaptable to different hardware configurations.

- **Known Issues:**
  - Streaming generation functionality is not available yet.

### v1.5.0

- **Main Improvements:**
  - Code refactoring: Optimized project structure for better readability and maintainability.
  - UI improvements: Modernized interface interactions for enhanced user experience.
  - Performance optimization: Reduced resource consumption and improved running efficiency.
  - Modular design: Clearer module division for easier feature expansion.
  - Compatibility enhancements: Improved support for various environments and additional platforms.

- **Important Changes:**
  - **Configuration:** Restructured v1.5.0 uses a new configuration format.
  - **API Changes:** Some API endpoints have been adjusted; users transitioning from v1.0.0 need to adapt to the new API rules.

### v1.6.0

- **Main Improvements:**
  - Codebase refactoring: Optimized frontend-backend communication via APIs to improve maintainability.
  - UI enhancement: Added a "Generating content..." real-time status indicator to elevate user experience.
  - Streaming transmission & generation: Implemented streaming support for content delivery and generation, ensuring smoother interactions.

### v1.6.1
- **Major Improvements**
  - Fix existing bugs
  - Fix missing dependency download in `scripts\model_downloader.py`
- **Issue Explanation
  - For the issue in [#3](https://github.com/WavesMan/DeepSeek-R1-Local-WebUI/issues/3) , 1.5B and other quantitative models (which have not been tested to exist) are model problems due to their quantitative nature and the “not answering the question” problem after a long run. It is recommended that you re-download the model and run `pip uninstall transformers` before running `python scripts\model_downloader.py` to re-install the dependencies.
  
### v1.6.2
- **Major improvements**
  - Refactored front-end, implemented with Vue3+JavaScript+Vite+Pinia 

### v1.7.0-1 (Pre-release)
- **Main Improvements:**
  - **CLI-based** startup simplifies operations.
  - Configurable frontend access paths.
- **Planned:**
  - Plugin system for extensibility.
  
---

## Configuration Items Explanation

### 1. In **config/webui.py**:

| Parameter Name | Default Value | Allowed Parameters/Range | Description |
| --- | --- | --- | --- |
| reserved_memory | 1 | 0 - infinite | Reserved VRAM to prevent model loading failures. |
| input_max_length | 2000 | Positive integer | Maximum length of input text. |
| min_length | 1 | Positive integer | Minimum length of generated text. |

### 2. In **config/generation.py**:

| Parameter Name | Default Value | Allowed Parameters/Range | Description |
| --- | --- | --- | --- |
| max_length | 500 | Positive integer | Maximum length of generated text. |
| num_beams | 1 | Positive integer | Beam Search beam count, controlling text diversity. |
| temperature | 0.7 | 0.0 to 1.0 | Controls the randomness of generated text; lower values are more deterministic, higher values are more random. |
| top_k | 50 | Positive integer | Top-K sampling parameter, controls the number of words considered during text generation. |
| top_p | 0.9 | 0.0 to 1.0 | Top-P sampling parameter, controls the cumulative probability threshold during text generation. |
| do_sample | True | True or False | Indicates whether to use sampling or greedy search for text generation. If False, greedy search is used. |

### 3.In **config/webui.py**:

| Parameter Name | Default Value | Allowed Parameters/Range | Description |
| --- | --- | --- | --- |
| host | "127.0.0.1" | String (IP address) | Host address for the WebUI service. |
| port | 5000 | 1024 to 65535 | Port number for the WebUI service. |

---

## Contributions and Feedback 

We welcome issues and pull requests to improve the project! If you have any questions or suggestions, please contact us via the following channels:

[GitHub Issues](https://github.com/WavesMan/DeepSeek-R1-Local-WebUI/issues): Submit an issue

---

## License 

This project follows the [MIT License](DeepSeek-R1_LICENSE) of DeepSeek-R1
<br>This project is based on the [MIT License](LICENSE) open source

---

## Thanks

- **DeepSeek Team** : Provide the **DeepSeek R1** model.
- **Flask** : Provides lightweight Web framework.
- **FontAwesome** : Provides icon resources.

---

## Sponsorship

Support the project by becoming a sponsor. Your support helps keep this project alive!

| Platform       | Link                                                                 |
|----------------|---------------------------------------------------------------------|
| 💖 afdian      | [Sponsor on Aifadian](https://afdian.net/a/wavesman)
| 💰 Alipay      | [Sponsor on AliPay](https://github.com/WavesMan/Disable-automatic-Windows-update/blob/main/src/AliPay.jpg)    |
| 🎁 Wechat      | [Sponsor on wechat](https://github.com/WavesMan/Disable-automatic-Windows-update/blob/main/src/WeChat.png)    |
| ⭐ Patreon     | [Sponsor on Patreon](https://patreon.com/Waves_Man)      |
| 🌟 PayPal      | [Donate via PayPal](https://paypal.me/wavesman)                |

---
I hope this `Readme-en.md` will help you present your project better! If there are other needs, please feel free to supplement or modify!