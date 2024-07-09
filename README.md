# Build AI-Powered Apps with OpenAI and Node.js

This repo is a companion to the [Build AI-Powered Apps with OpenAI and Node.js]

## Errata

**Document QA Query Function Lesson**


Install the Langchain community module

```bash
npm i @langchain/community
````

Import the loaders

```javascript
import { PDFLoader } from '@langchain/community/document_loaders/fs/pdf'
import { YoutubeLoader } from '@langchain/community/document_loaders/web/youtube'
```

Create the loaders using the community methods:

In `docsFromYTVideo`:

```javascript
const loader = YoutubeLoader.createFromUrl(video, { language: 'en', addVideoInfo: true, })
return loader.load( new CharacterTextSplitter({ separator: ' ', chunkSize: 2500, chunkOverlap: 200, }) )
```

In `docsFromPDF`: 

```javascript
const docsFromPDF = async () => { const loader = new PDFLoader('./xbox.pdf')
return loader.load( new CharacterTextSplitter({ separator: ' ', chunkSize: 2500, chunkOverlap: 200, }) ) }
```