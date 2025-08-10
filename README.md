Move to week 3 file:
https://colab.research.google.com/drive/1QYSlahOkqKKHBZN1-F_KzbHzXsM1cxD1?usp=sharing
https://www.youtube.com/watch?v=eMlx5fFNoYc


# A 10-Week Effort to Learn About Transformers for Epidemic Forecasting

📖 **[View this course online](https://aflaxman.github.io/learning-about-transformers-for-epidemic-forecasting/){:target="_blank"  rel="noopener"}**

## Course Overview
A streamlined self-study course bridging epidemiological modeling and modern transformer architectures for time series forecasting.

**Meeting Time**: Wednesdays 1:05-2:00 PM  
**Duration**: July 2 - September 3, 2025

## Course Schedule
- **Week 1** (July 2): Epidemiological Foundations
- **Week 2** (July 9): Time Series Fundamentals  
- **Week 3** (July 16): Understanding Transformers
- **Week 4** (July 23): Decoder-Only Transformers (GPT-style)
- **Week 5** (July 30): Transformers Meet Time Series
- **Week 6** (August 6): Chronos Foundation Model
- **Week 7** (August 13): Beyond Numbers - Text and Time Series
- **Week 8** (August 20): Time Series from Tables
- **Week 9** (August 27): Synthetic Data Strategies
- **Week 10** (September 3): Fine-tuning & Course Wrap-up


## Weekly Meeting Format
- **First 30 minutes**: Discussion of the week's reading and concepts
- **Next 20 minutes**: Share mini-project progress and challenges
- **Final 10 minutes**: Preview of next week's topic
- **Optional**: Stay after for informal collaboration

## Before the First Meeting
Please complete by July 2:
1. Set up Python environment (see Tools & Setup section)
2. Create a GitHub repository for your course work
3. Download at least one dataset from Project Tycho
4. Read Week 1's paper
5. Optional: Watch [But what is a GPT?](https://www.3blue1brown.com/lessons/gpt){:target="_blank"  rel="noopener"} by 3Blue1Brown for intuition on decoder-only models

## Week 1: Epidemiological Foundations
**Wednesday, July 2, 2025 | 1:00 PM**

📁 **[Week 1 Materials & Instructions](week-01/README.md)**

### Core Reading
- **Mathematical Models in Infectious Disease Epidemiology** - [PMC7150075](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7150075/){:target="_blank"  rel="noopener"}
  - Focus on Sections 1-3 (SIR/SEIR models)

### Mini-Project
**Simple SEIR Simulator**
- Implement basic SEIR model in Python
- Plot epidemic curves for 3 different R₀ values
- Calculate peak timing and final attack rate

### Resources
- [StarSim Examples](https://starsim.org/#examples){:target="_blank"  rel="noopener"}

---

## Week 2: Time Series Fundamentals
**Wednesday, July 9, 2025 | 1:00 PM**

📁 **[Week 2 Materials & Instructions](week-02/README.md)**

### Core Reading
- **An Overview of Forecast Analysis with ARIMA Models during the COVID-19 Pandemic: Methodology and Case Study in Brazil** - [PMC10631421](https://doi.org/10.3390/math11143069){:target="_blank"  rel="noopener"}
  - Focus on ARIMA section

### Mini-Project
**Flu Forecasting with ARIMA**
- Download influenza data from [Project Tycho](https://www.tycho.pitt.edu/){:target="_blank"  rel="noopener"}
- Fit ARIMA model to one state's data
- Make 4-week ahead forecasts

### Resources
- [How to Create an ARIMA Model for Time Series Forecasting in Python](https://machinelearningmastery.com/arima-for-time-series-forecasting-with-python/){:target="_blank"  rel="noopener"}

---

## Week 3: Understanding Transformers
**Wednesday, July 16, 2025 | 1:00 PM**

### Core Reading
- **The Illustrated Transformer** - [Jay Alammar's Blog](https://jalammar.github.io/illustrated-transformer/){:target="_blank"  rel="noopener"}

### Mini-Project
**Attention Visualization**
- Implement scaled dot-product attention in NumPy
- Create attention heatmap for a toy sequence

---

## Week 4: Decoder-Only Transformers 
**Wednesday, July 23, 2025 | 1:00 PM**

### Core Reading
- **Decoder-Only Transformers: The Workhorse of Generative LLMs** - [Cameron Wolfe](https://cameronrwolfe.substack.com/p/decoder-only-transformers-the-workhorse){:target="_blank"  rel="noopener"}

### Mini-Project
**Autoregressive Generation for Time Series**
- Understand causal masking vs. bidirectional attention
- Implement simple next-value prediction
- Compare GPT-style generation with encoder-decoder approach
- Explore why decoder-only works well for time series

### Code Hint
```python
# Causal masking example
import numpy as np
# Create a mask where future values are hidden
seq_len = 5
causal_mask = np.tril(np.ones((seq_len, seq_len)))
print(causal_mask)  # Lower triangular matrix
```

---

## Week 5: Transformers Meet Time Series
**Wednesday, July 30, 2025 | 1:00 PM**

### Core Reading
- **Probabilistic Time Series Forecasting with Transformers** - [Hugging Face Blog](https://huggingface.co/blog/time-series-transformers){:target="_blank"  rel="noopener"}

### Mini-Project
**First Transformer Forecast**
- Use Hugging Face's TimeSeriesTransformer
- Train on synthetic sine wave with trend
- Visualize predictions with confidence intervals

### Code Start
```python
from transformers import TimeSeriesTransformerForPrediction
```

---

## Week 6: Chronos Foundation Model
**Wednesday, August 6, 2025 | 1:00 PM**

### Core Reading
- **Chronos: Learning the Language of Time Series** - [arXiv:2403.07815](https://arxiv.org/abs/2403.07815){:target="_blank"  rel="noopener"}
  - Focus on Sections 1-3 and 5

### Mini-Project
**Zero-Shot Disease Forecasting**
- Install Chronos: `pip install chronos-forecasting`
- Apply to COVID-19 data for one country
- Compare tiny vs. small model performance

### Quick Start
```python
from chronos import ChronosPipeline
pipeline = ChronosPipeline.from_pretrained("amazon/chronos-t5-tiny")
```

---

## Week 7: Beyond Numbers - Text and Time Series
**Wednesday, August 13, 2025 | 1:00 PM**

### Core Reading
- **PandemicLLM Overview** - [arXiv:2404.06962](https://arxiv.org/abs/2404.06962){:target="_blank"  rel="noopener"}
  - Read abstract and methods section

### Mini-Project
**Text-Enhanced Forecasting with Decoder-Only Models**
- Create text descriptions of epidemic phases ("rapid growth", "plateau", etc.)
- Use a pre-trained GPT-2 or similar decoder-only model
- Explore how PandemicLLM uses ordinal classification tokens

---

## Week 8: Time Series from Tables
**Wednesday, August 20, 2025 | 1:00 PM**

### Core Reading
- **From Tables to Time: How TabPFN-v2 Outperforms Specialized Time Series Forecasting Models** - [doi.org:10.48550/arXiv.2501.02945](https://doi.org/10.48550/arXiv.2501.02945){:target="_blank"  rel="noopener"}
  - SoTA time series forecasts in Jan 2025, still in the top tier of [GIFT-Eval](https://huggingface.co/spaces/Salesforce/GIFT-Eval)

### Mini-Project
**Compare on epidemics**
- Use 5 states/countries
- Use 2 disease signals
- Apply Chronos, PandemicLLM, TabPFN, and compare results

---

## Week 9: Synthetic Data Strategies
**Wednesday, August 27, 2025 | 1:00 PM**

### Core Reading
- **KernelSynth Section from Chronos Paper** - [arXiv:2403.07815](https://arxiv.org/abs/2403.07815){:target="_blank"  rel="noopener"}
  - Section 4.2 only

### Mini-Project
**Generate Synthetic Outbreaks**
- Create 10 synthetic epidemic curves
- Vary peak timing and height
- Train a model on synthetic, test on real data

---

## Week 10: Fine-tuning Foundation Models
**Wednesday, September 3, 2025 | 1:00 PM**

### Core Reading
- **Fine-tuning Conceptual Guide** - [Hugging Face PEFT Docs](https://huggingface.co/docs/peft/index){:target="_blank"  rel="noopener"}
  - Just the conceptual guide

### Mini-Project
**Disease-Specific Fine-Tuning**
- Take pre-trained Chronos-tiny
- Fine-tune on one specific disease (e.g., measles)
- Compare zero-shot vs. fine-tuned on test data


---

## Tools & Setup

### Essential Libraries
```bash
pip install pandas numpy matplotlib
pip install statsmodels
pip install transformers
pip install chronos-forecasting
pip install torch  # or tensorflow
```

### Compute Resources
- Most projects can run on Google Colab free tier
- Chronos tiny/small models work on CPU

---

## Weekly Time Commitment
- **Reading**: 1-3 hours
- **Mini-project**: 3-6 hours
- **Meeting to Discuss**: 1 hour
- **Total**: 5-10 hours per week

## Success Tips
1. Focus on understanding concepts over implementation details
2. Start simple - you can always add complexity
3. Document your learning journey
4. Share your work (slack, GitHub, blog posts)
5. Join communities ([Hugging Face Forums](https://discuss.huggingface.co/){:target="_blank"  rel="noopener"})
6. Pay special attention to Week 4 - decoder-only architectures are crucial for modern LLMs


By course end, you'll have:
- Practical experience with transformer-based epidemic forecasting
- Deep understanding of decoder-only vs. encoder-decoder architectures
- A portfolio of 8+ small projects
- Foundation for further research or applications
