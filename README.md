# CircleCI Doc Assistant

## Rationale
[CircleCI Docs](https://circleci.com/docs/) is a big site with tons of documentation, how do we make it easy for users to discover the content? The CircleCI Doc site provides a search and returns the pages that contain the search keyword. Now with these LLMs, I believe it'd bring the search to the next level, by providing a doc assistant to answer any questions.

## Approach

**Context injection**

Search the docs and provide relevant content based on user’s input, put them in the prompt and let GPT model leverage this context and give the answer.

To decide which piece of the document is most relevant, we can use OpenAI’s text embeddings. The Embedding API takes a piece of text and spits out a vector of float point numbers. An embedding is a vector (list) of floating point numbers. The distance between two vectors measures their relevance.

One of the pros of this approach is that we can provide up-to-date and accurate answers without retraining the model.
