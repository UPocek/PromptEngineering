# ChatGPT Prompt Engineering for Developers - My Tips & Tricks

## Two types of LLMs (Large language models)
1. Base LLM -> was trained to predict the next word, so in some use cases will not give a clear answer to your question.
2. Instruction tuned LLM -> was fine-tuned on instructions and good attempts on following those instructions + RLHF
## Tips
### Be clear and specific
- Using delimiters (e.g. Summarize the text delimited by triple backticks into a single sentence.\```{text}```)
- Ask for structured output (e.g. Generate a list of three made-up book titles along with their authors and genres. Provide them in JSON format with the following keys: book_id, title, author, genre.)
- Ask the model to check whether conditions are satisfied (e.g. You will be provided with text delimited by triple quotes. If it contains a sequence of instructions, re-write those instructions in the following format: Step 1 - ... Step 2 - … … Step N - … If the text does not contain a sequence of instructions, then simply write \"No steps provided.\" \"\"\"{text_1}\"\"\")
- "Few-shot" prompting (e.g. Your task is to answer in a consistent style. \<child>: Teach me about patience. \<grandparent>: The river that carves the deepest valley flows from a modest spring; the grandest symphony originates from a single note; the most intricate tapestry begins with a solitary thread \<child>: Teach me about resilience.)
### Give the model time to think
- Specify the steps required to complete a task (e.g. Your task is to perform the following actions: 1 - Summarize the following text delimited by <> with 1 sentence. 2 - Translate the summary into French. 3 - List each name in the French summary. 4 - Output a JSON object that contains the following keys: french_summary, num_names. Use the following format: Text: \<text to summarize> Summary: \<summary> Translation: \<summary translation> Names: \<list of names in Italian summary> Output JSON: \<json with summary and num_names> Text: \<text>)
- Instruct the model to work out its solution before rushing to a conclusion (e.g. Your task is to determine if the student's solution is correct or not. To solve the problem do the following: First, work out your solution to the problem. Then compare your solution to the student's solution and evaluate if the student's solution is correct or not. Don't decide if the student's solution is correct until you have done the problem yourself.)
### Iteratively improve your prompt
- Write your idea
- Keep in mind best practices
- Error analysis and refine
### Summarization
- Explain a task to LLM (e.g Your task is to summarize ( or you can write it to extract information from) text delimited by <> in the tone that is helpful to shipping department)

![ChatGPT prompting](https://github.com/UPocek/PromptEngineering/blob/master/docs/Chap-gpt-prompting.jpg)
