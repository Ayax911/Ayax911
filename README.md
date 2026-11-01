<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,14,18&height=210&section=header&text=Julian%20Ojeda%20Aviles&fontSize=44&fontColor=ffffff&fontAlignY=38&animation=fadeIn&desc=Systems%20Engineering%20%7C%20Federated%20Learning%20%7C%20Medical%20Imaging&descSize=17&descAlignY=60" alt="Julian Ojeda Aviles banner" />

<a href="https://github.com/Ayax911">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&pause=1200&color=2F81F7&center=true&vCenter=true&width=640&lines=Young+Researcher+at+the+MIRP+group+(ITM);Federated+learning+for+mammography;Deep+learning+and+software+engineering;Medell%C3%ADn%2C+Colombia" alt="Typing animation" />
</a>

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_9-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Weights & Biases](https://img.shields.io/badge/Weights_&_Biases-FFBE00?style=for-the-badge&logo=weightsandbiases&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

</div>

---

## About me

```python
from dataclasses import dataclass, field


@dataclass
class Julian:
    name: str = "Julian Ojeda Aviles"
    location: str = "Medellín, Colombia"
    studying: str = "Systems Engineering @ Instituto Tecnológico Metropolitano (ITM)"
    role: str = "Joven Investigador e Innovador @ MIRP, semillero MIRI2G"
    focus: list[str] = field(default_factory=lambda: [
        "federated learning",
        "medical image classification",
        "deep learning",
        "software engineering",
    ])

    def research_question(self) -> str:
        return ("How does federated training compare with centralized training "
                "for binary mammography classification on naturally partitioned data?")


if __name__ == "__main__":
    print(Julian().research_question())
```

- Systems Engineering student at ITM, in the bridging cycle (propedéutico) that follows my completed Technology in Software Development degree.
- Young researcher in the MIRP group (Máquinas Inteligentes y Reconocimiento de Patrones, Intelligent Machines and Pattern Recognition), part of the MIRI2G research seedbed.

---

## Research focus

| Line of work | What I do |
|---|---|
| Mammography | Binary classification (benign vs. malignant) with a centralized baseline and a federated framework, comparing aggregation strategies |
| Skin lesions | Experiments with FLamby on the Fed-ISIC2019 benchmark, used as a reference point for the mammography work |
| Interpretability | Grad-CAM tooling to inspect what the trained classifiers look at |

---

## Featured projects

| Project | Description | Stack |
|---|---|---|
| [**FedMammoBench**](https://github.com/Ayax911/FedMammoBench) | Mammography classification benchmark: centralized baseline plus a federated layer on Flower with real gRPC deployment | `Python` `PyTorch` `Flower` `Docker` |
| [**FLamby (fork)**](https://github.com/Ayax911/FLamby) | Fork of the FLamby benchmark used for my Fed-ISIC2019 experiments | `Python` |
| [**QualityWineML**](https://github.com/Ayax911/QualityWineML) | Wine quality classification pipeline with a Streamlit app that walks through each stage | `Python` `scikit-learn` `Streamlit` |
| [**ClothingStore**](https://github.com/Ayax911/ClothingStore) | Layered REST API with JWT authentication and EF Core migrations | `C#` `.NET 9` `SQL Server` |

<details>
<summary><b>FedMammoBench in more detail</b></summary>
<br/>

- ResNet50 backbone pretrained on RadImageNet, trained in PyTorch.
- Validated centralized baseline, with the federated layer built on top of it.
- Federated strategies in the code: FedAvg, FedProx, SCAFFOLD, FedAdam and FedYogi.
- Natural partitions by source dataset: one federated node per dataset (CDD-CESM, CMMD, INbreast, KAU-BCMD).
- Experiments tracked through YAML configs, Weights & Biases and a consolidated experiment registry.
- Grad-CAM entrypoint for visual explanations.

</details>

<details>
<summary><b>QualityWineML and ClothingStore in more detail</b></summary>
<br/>

- QualityWineML: data loading, cleaning, feature engineering, comparison of Random Forest, XGBoost, LightGBM and MLP models, hyperparameter search, and a Streamlit app.
- ClothingStore: API, Application, Domain and Persistence layers on ASP.NET Core; clients, products, purchases and purchase details; BCrypt password hashing and refresh tokens.

</details>

---

## Quick look

<details>
<summary><b>Run a FedMammoBench experiment</b></summary>

```bash
# Centralized baseline
python -m src.cli --config configs/exp05_fedmammobench_full_weighted.yaml

# Federated: one server process and one process per node
python -m src.federated.server --config configs/federated/exp40_fedavg_full/server.yaml
python -m src.federated.client --config configs/federated/exp40_fedavg_full/node_cmmd.yaml

# Or the whole federation with Docker
EXPERIMENT=exp40_fedavg_full docker compose -f docker-compose.federated.yaml up
```

</details>

---

## Other work

- Team LAKA qualified for the final round of CODEFEST AD ASTRA 2026, organized by the Colombian Aerospace Force and Universidad de los Andes. Our project was a vector knowledge base evaluated with NDCG@10 and F1@3.

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,14,18&height=100&section=footer" alt="footer" />

</div>
