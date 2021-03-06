# Anuvaad
State of the art translation models for Indic languages.


# Installation

```bash
# CPU pytorch will be installed if torch is not installed
pip install --upgrade anuvaad
```

# Usage

**As a Python module**

```python
from anuvaad import Anuvaad
anu = Anuvaad("english-telugu")

# Single sentence translation
# beam_size is optional and defaults to 4
anu.anuvaad("YS Jagan is the chief minister of Andhra Pradesh.")
# "వైఎస్ జగన్ ఆంధ్రప్రదేశ్ ముఖ్యమంత్రి."

# Batch translation
anu.anuvaad(["YS Jagan is the chief minister of Andhra Pradesh.",
            "Nara Lokesh suffered a humiliating defeat in Mangalagiri."])
# ['వైఎస్ జగన్ ఆంధ్రప్రదేశ్ ముఖ్యమంత్రి.', 'మంగళగిరిలో నారా లోకేష్కు అవమానకరమైన ఓటమి ఎదురైంది.']

```

**As a service**
```bash
# Starting the api service
docker run -it -e BATCH_SIZE=1 -p 8080:8080 notaitech/anuvaad:english-telugu

# Running a prediction
curl -d '{"data": ["YS Jagan is the chief minister of Andhra Pradesh."]}' -H "Content-Type: application/json" -X POST http://localhost:8080/sync
```


|Available Models   | 
|--------|
|english-telugu | 
|english-tamil | 
|english-malayalam | 
|english-kannada | 
|english-marathi | 
|english-hindi | 
