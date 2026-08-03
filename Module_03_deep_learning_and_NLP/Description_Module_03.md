# Deep Learning, Computer Vision, and Natural Language Processing Framework

This repository contains the syllabus, implementation steps, and structural guidelines for the machine learning modules. The curriculum progresses from foundational dense neural network architectures to convolutional networks for computer vision, classic NLP pipelines, and transfer learning with pre-trained transformer models.

---

## Week 1: Neural Network Design and Architecture Auditing

### Collaborative Activity: Dense Architecture Design Practice
A "sandbox" experimentation environment where the goal is not merely to get a network working, but for the team to understand the impact of each design decision. Teams test different configurations to solve a classification problem and audit their own results.

### Phase 1: Building Architectures
Each team trains three variants for comparison:
*   **Model A — The Minimalist:** A single, small hidden layer.
*   **Model B — The Deep One:** Multiple hidden layers (Deep Learning).
*   **Model C — The Optimized One:** Uses Dropout, Adam, and regularization.

### Phase 2: Monitoring and Audit Roundtable
Collectively analyzing the Loss and Accuracy curves:
*   Visually identifying the Overfitting point in each model.
*   Discussing the impact of activation functions and the use of `EarlyStopping` for generalization.

### Submission Format
A single `.ipynb` file per team including:
1.  **Identification:** List of team members and roles (Network Architect, Data Specialist, Metrics Analyst).
2.  **Evidence:** Executed cells for all three models validating the group's experimentation.
3.  **Answers:** Critical analysis of the architectures' performance.

---

## Week 2: Computer Vision and Automated Classification with CNNs

### Scenario: Fashion E-commerce
The mission is to optimize the digital supply chain of a leading fashion company by developing a Convolutional Neural Network (CNN) capable of automatically classifying thousands of product images, eliminating bottlenecks and human labeling errors.

### Phase 1: Data Wrangling for Images
*   **Native Loading:** Importing `Fashion MNIST` from Keras.
*   **Normalization:** Scaling pixel values to the [0, 1] range.
*   **Reshape:** Adjusting tensors to 4 dimensions (Batch, 28, 28, 1) to include the color channel.

### Phase 2: CNN Design and Training
**Architecture Requirements:**
*   2 `Conv2D` layers (ReLU) + 2 `MaxPooling2D` layers.
*   A `Flatten` layer followed by Dense layers.
*   Output layer: 10 neurons with `softmax` activation.

**Compilation and Epochs:**
Using the Adam optimizer and `sparse_categorical_crossentropy` loss function. Training for a minimum of 10 epochs.

### Phase 3: Analytical Evaluation
*   Generating Loss and Accuracy evolution plots.
*   **Business Question:** Which categories does the model confuse most often? Explaining the financial impact of these errors and how they would be addressed.

---

## Week 3: NLP Workshop — Language Processing and Sentiment Analysis

### Technical Requirements
Setting up the environment with the essential libraries for linguistic processing: spaCy (`es_core_news_lg`), TextBlob, Gensim (LDA), and Pandas.

### Phase 1: Ingestion and Sentiment
*   **Technical Cleaning:** Loading `feedback_clientes.csv` and applying normalization: lowercasing, stopword removal, and Lemmatization with spaCy.
*   **Sentiment Classification:** Categorizing feedback as Positive, Neutral, or Negative and generating a percentage distribution chart to visualize overall feedback health.

### Phase 2: Similarity and Topic Modeling
*   **Embeddings (Vectors):** Defining an "Ideal Comment" and calculating semantic similarity against the dataset, identifying the 5 closest records.
*   **LDA on Negative Feedback:** Using Gensim to identify 3 topics among the complaints, assigning analytical labels (e.g., "Pricing," "Support") based on keywords.

### Submission Guidelines (Moodle)
Individual or compressed file: `LastName_FirstName_NLP_Workshop.ipynb`
*   Markdown cells with clear explanations.
*   Charts with professional titles and axis labels.
*   Final paragraph with conclusions on which areas the company should improve.

---

## Week 4: Transfer Learning and Fine-Tuning with Transformers

### Phase 1: Environment and Model Setup
Preparing Hugging Face tools to perform fine-tuning on a pre-trained language model.
*   **Installation:** Setting up `transformers`, `datasets`, and `accelerate`.
*   **Model Selection:** Using a base model such as `bert-base-multilingual-cased` and loading its corresponding tokenizer.

### Phase 2: Dataset Preparation
Loading a classification dataset (minimum 2 categories) and applying the tokenizer to convert text into the format required by the model.

### Phase 3: Transfer Learning Implementation
**Critical Step: Freezing Layers**
Implementing `requires_grad = False` on the model's base layers. This ensures only the final classification head is trained, leveraging the LLM's prior knowledge.

### Phase 4: Training and Evaluation
**Execution with Trainer:**
*   Configuring `TrainingArguments` (epochs, batch size).
*   Running training and performing a test inference with a new sentence.
*   Displaying the winning category and its confidence score.

### Submission Format (Moodle)
1.  **Notebook:** Link with read permissions.
2.  **Report:** Technical explanation of layer freezing along with a screenshot of the prediction results.
