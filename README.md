# LLM RAG Tutorials
    RAG(Retrieval-Augmented Generation)는 대규모 언어 모델의 출력을 최적화하여 응답을 생성하기 전에 학습 데이터 소스 외부의 신뢰할 수 있는 지식 베이스를 참조하도록 하는 프로세스입니다. 대규모 언어 모델(LLM)은 방대한 양의 데이터를 기반으로 학습되며 수십억 개의 매개 변수를 사용하여 질문에 대한 답변, 언어 번역, 문장 완성과 같은 작업에 대한 독창적인 결과를 생성합니다. RAG는 이미 강력한 LLM의 기능을 특정 도메인이나 조직의 내부 지식 기반으로 확장하므로 모델을 다시 교육할 필요가 없습니다. 이는 LLM 결과를 개선하여 다양한 상황에서 관련성, 정확성 및 유용성을 유지하기 위한 비용 효율적인 접근 방식입니다.
## HW Info
    1. CPU: i9-11900KB
    2. MEM: 64 GB
    3. GPU: RTX 3060 12GB
## Requirements
    1. Ubuntu 22.04
    2. Docker & docker-compose (or podman, podman-compose)
    3. Miniconda3
## Tutorials
### Create pgvector image
```bash
git clone --branch v0.7.1 https://github.com/pgvector/pgvector.git
cd pgvector
docker build --pull --build-arg PG_MAJOR=16 -t watchtek/pgvector .
cd ..
```
### Start Vector database
```bash
git clone https://github.com/skytelan3/rag_tutorials
cd rag_tutorials/docker-compose
docker-compose up -d
cd ..
```
### Create Miniconda Env
```bash
conda env create --file environment.yml
```
### Start jupyterlab
```bash
conda activate rag_tutorials
./jupyterlab.sh
```