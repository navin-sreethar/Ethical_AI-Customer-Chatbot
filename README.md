# Customer-AI-Chatbot

## Ethical AI-Powered Customer Service Chatbot

### Project Overview
As AI-powered chatbots are increasingly adopted for customer support, ethical concerns such as bias, privacy, and transparency become critical. This project presents an AI chatbot that prioritizes ethical AI design by integrating privacy-preserving preprocessing, bias detection, explainable decision-making, and responsible escalation. Built using Logistic Regression with TF-IDF features, the chatbot serves as a robust and transparent solution for real-time customer service.

### Motivation
The chatbot is designed to align machine learning efficiency with responsible AI practices. Benefits include:
- **Fairness and Inclusivity**: Proactively detects and flags potentially biased inputs to prevent discrimination.
- **Transparency and Trust**: Uses LIME-based explanations for low-confidence decisions to improve user understanding.
- **Effective Customer Service**: Maintains ethical standards while delivering accurate and responsive customer interactions.

### Problem Description
Developing an ethical AI chatbot presents several key challenges:
- **Bias in AI Responses**: Addressing latent bias in training data and user queries.
- **Explainability**: Enabling users to understand model behavior, particularly in low-confidence scenarios.
- **Human-AI Collaboration**: Escalating ambiguous or sensitive cases to human agents to avoid harm.

### Literature Review
This project builds on foundational and recent work in ethical NLP and customer support automation:
- Toxic content detection and fairness: Garlapati et al. (2022); Kumar and Kanisha (2022)
- Explainability in AI: Ribeiro et al. (2016); Doshi-Velez and Kim (2017)
- AI in customer service: Sood et al. (2024); Asif et al. (2024); Waladi et al. (2024); Nithya et al. (2024)

### Model/Algorithm
- **TF-IDF Vectorization**:  N-gram range (1,2), max 5000 features, English stop words
- **Logistic Regression**: Balanced class weights, 1000 max iterations, lbfgs solver
**Ethical Guardrails**: 
- Rejects messages with PII (emails, phone numbers, credit cards, SSNs)
- Flags biased input based on sensitive attributes
- Escalates low-confidence responses to human agents
- Explains predictions using LIME

### Datasets
- **Customer Support on Twitter Dataset (Hugging Face)**:  A real-world dataset used for intent classification (support, positive, other). Labels were generated using keyword-based heuristics and balanced through undersampling.

### Evaluation Metrics
- Accuracy: 0.987
- Precision: 0.980
- Recall: 0.980
- F1 Score: 0.987

### Analysis
- **Error Analysis**: Shows the system's reliability and triggers for escalation.
- **Bias Analysis**: Flags references to gender, race, religion, or similar sensitive attributes.
- **Explainability with LIME**: Displays key tokens influencing the model's decisions for transparency.

### Example Interactions

**Example 1**  
**User:** I can't access my account  
**Chatbot:** Let me help you with that.  
**Prediction:** support  
**Confidence:** 1.00  

**Example 2**  
**User:** connect me to an agent  
**Chatbot:** Connecting you to a human representative.  
**Prediction:** support  
**Confidence:** 0.67  
**LIME Explanation:**  
- agent: 0.0052  
- connect: -0.0044  

**Example 3**  
**User:** this box is sealed tight and hard to open  
**Chatbot:** Connecting you to a human representative.  
**Prediction:** other  
**Confidence:** 0.51  
**LIME Explanation:**  
- box: 0.0029  
- open: 0.0011  
- tight: -0.0031  


### Conclusion

This project implemented an ethical AI-powered chatbot for customer support, emphasizing responsible AI practices alongside reliable performance. The system incorporates:

- **Privacy-preserving preprocessing** to detect and redact sensitive user data.
- **Confidence-based escalation** to hand off uncertain queries to human agents.
- **Bias detection** to flag language referencing sensitive demographic attributes.
- **LIME-based explanations** to promote transparency and interpretability.

Together, these components create a chatbot that not only responds to customer queries but also operates within ethical boundaries, promoting fairness, privacy, and accountability. Future improvements include expanding the model’s linguistic understanding using transformers, enhancing PII detection with named entity recognition, and integrating demographic auditing tools.

### References

- Sood, P., Tanwar, H., Singh, J., Ruhela, A. K., Gupta, N., & Kumar, R. (2024). *Revolutionizing Customer Service: An AI-powered Chatbot Approach using Advanced NLP Techniques*. 2024 IEEE DELCON. https://doi.org/10.1109/DELCON64804.2024.10866078  
- Asif, M., Manan, A., Rehman, A. M. U., Asghar, M. N., & Umair, M. (2024). *AI-Driven Chatbot for Intrusion Detection in Edge Networks: Enhancing Cybersecurity with Ethical User Consent*. 2024 HITE. https://doi.org/10.1109/HITE63532.2024.10777142  
- Waladi, C., Lamarti, M. S., & Khaldi, M. (2024). *Transforming Customer Experiences with Customer-Centric AI-Powered Chatbots in the Fourth Industrial Revolution*. 2024 MSCC. https://doi.org/10.1109/MSCC62288.2024.10697060  
- Nithya, M., S, S., S, L., & B, M. (2024). *Revolutionizing Customer Experience with AI-Powered Chat bots and Virtual Assistants*. 2024 ICSES. https://doi.org/10.1109/ICSES63760.2024.10910297

