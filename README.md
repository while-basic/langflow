<!-- Title -->

# LangFlow

~ A User Interface For LangChain

LangFlow is a GUI for LangChain, designed with react-flow to provide an effortless way to experiment and prototype flows with drag-and-drop components and a chat box.

## 📦 Installation
### <b>Locally</b>
You can install LangFlow from pip:

```shell
pip install langflow
```

Next, run:

```shell
python -m langflow
```
or
```shell
langflow
```

#### API Usage

You can use Langflow directly on your browser, or use the API endpoints on Jina AI Cloud to interact with the server.

  <details>
  <summary>Show API usage (with python)</summary>

  ```python
  import json
  import requests

  FLOW_PATH = "Time_traveller.json"

  # HOST = 'http://localhost:7860'
  HOST = 'https://langflow-f1ed20e309.wolf.jina.ai'
  API_URL = f'{HOST}/predict'

  def predict(message):
      with open(FLOW_PATH, "r") as f:
          json_data = json.load(f)
      payload = {'exported_flow': json_data, 'message': message}
      response = requests.post(API_URL, json=payload)
      return response.json()


  predict('Take me to 1920s Bangalore')
  ```

  ```json
  {
    "result": "Great choice! Bangalore in the 1920s was a vibrant city with a rich cultural and political scene. Here are some suggestions for things to see and do:\n\n1. Visit the Bangalore Palace - built in 1887, this stunning palace is a perfect example of Tudor-style architecture. It was home to the Maharaja of Mysore and is now open to the public.\n\n2. Attend a performance at the Ravindra Kalakshetra - this cultural center was built in the 1920s and is still a popular venue for music and dance performances.\n\n3. Explore the neighborhoods of Basavanagudi and Malleswaram - both of these areas have retained much of their old-world charm and are great places to walk around and soak up the atmosphere.\n\n4. Check out the Bangalore Club - founded in 1868, this exclusive social club was a favorite haunt of the British expat community in the 1920s.\n\n5. Attend a meeting of the Indian National Congress - founded in 1885, the INC was a major force in the Indian independence movement and held many meetings and rallies in Bangalore in the 1920s.\n\nHope you enjoy your trip to 1920s Bangalore!"
  }
  ```

  </details>
