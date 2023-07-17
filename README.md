# Auto-Chunk

Auto-Chunk is a Python class that is designed to chunk large documents into smaller, "smart" chunks. These chunks are optimized for retrieval augmented generation tasks, such as summarization, translation, and question generation.

## Problem

When dealing with large documents, it can be difficult to work with them as a whole. Breaking them down into smaller chunks can make them more manageable, but this can also introduce new problems. 

This is a big issue for Retrieval Augmented Generation, where naively chunked document (fixed size) might destroy meaning from the original document.

For example:

- Losing context: If a chunk splits a class or function in a code base, it can be difficult to understand the code in that chunk without the context of the rest of the class or function.

- Breaking sentences: In legal documents or other text-heavy documents, splitting a chunk in the middle of a sentence can make it difficult to understand the meaning of the text.

- Suboptimal chunks: Simply splitting a document into equal-sized chunks may not be the best approach for all tasks. For example, for summarization, it may be better to split the document into chunks that represent complete thoughts or ideas.


## Benefits
Auto-Chunk offers several benefits for document chunking, including:

- **Smart chunking**: Auto-Chunk is designed to create "smart" chunks that are optimized for retrieval augmented generation tasks, such as summarization, translation, and question generation. This means that the chunks are not just randomly split, but are split in a way that makes them more useful for specific tasks.

- **Customizable**: Auto-Chunk allows you to customize the chunking process by specifying the expected task, maximum number of tokens allowed in a chunk, and document type. This means that you can tailor the chunking process to your specific needs.

- **First pass**: Auto-Chunk runs a first pass on the document to generate instructions for chunking. This means that the chunking process is more informed and can produce better results.

- **OpenAI integration**: Auto-Chunk integrates with OpenAI to provide chat completion for the chunking process. This means that the chunking process can be more interactive and produce better results.


## Usage
To use Auto-Chunk, you will need to create an instance of the llm_chunker class and pass in the following parameters:

* expected_task: The task for which the chunker is used (e.g. "summarization", "translation", "question_generation")
* max_tokens: The maximum number of tokens allowed in a chunk
* document_type: A description of the document type (e.g. "news", "wikipedia", "scientific_paper", "rfc_specification")
* openai_api_key: Your OpenAI API key

Once you have created an instance of the llm_chunker class, you can load a document using the load_document method:

```
auto_chunker.load_document('path/to/document.txt')
```

You can then run the first pass on the document using the first_pass method:

```
auto_chunker.first_pass()
```

This will split the document into naive sections and prepare chunking instructions for each section.

## Work in progress

### first_pass()
> 🚧 find a prompting technique to make the first pass generate instructions for the second one;

TODO: 

- [ ] try with openai functions
- [ ] be more precise with the parameters usage
- [ ] try few shot


### chunk()

> 🚧 highly depends on the result of the first pass

