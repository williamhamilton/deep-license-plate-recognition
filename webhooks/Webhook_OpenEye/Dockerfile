FROM python:3.11-slim
ENV PYTHONUNBUFFERED=1
WORKDIR /app

RUN apt-get update\
    && apt-get install --no-install-recommends -y curl libgl1\
    && rm -rf /var/lib/apt/lists/*\
    && pip install --upgrade pip

# Copy python dependecies file
COPY requirements.txt .

RUN pip install -r requirements.txt

# Copy source code
COPY . /app/

CMD [ "python3", "main.py", "--host", "0.0.0.0" ]

