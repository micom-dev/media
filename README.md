## Environmental growth media for MICOM :seedling: :earth_africa: :pizza:

This repo contains recipes and artifacts for growth media with use in MICOM. Community contributions are very much welcome and invited :smile:

## How to add a new recipe/medium

If you don't have one already create a new Qiime 2 environment along with q2-micom. See [here on how to do that](https://github.com/micom-dev/q2-micom/blob/master/docs/README.md#installation). After activating the environment add Jupyter Lab as well:

```bash
conda install jupyter-lab
```

Make a fork of the repository (Fork button on the upper right) and clone it onto your own machine:

```bash
git clone USER/media
```

Create a new branch and start Jupyter Lab:

```
cd USER/media
git checkout -b my_medium_description
jupyter lab
```

Create a new Jupyter Notebook that contains the code and reasoning for creating the new medium. The notebook must produce a new Qiime 2 artifact medium in the "media" subfolder. See the [AGORA notebook](recipe/agora.ipynb) for an example. The name of the artifact should indicate the following:

1. the condition/context (western diet, nitrogen-limited, rich, etc.)
1. the environment (gut, soil, ocean, etc.)
2. The model database/ID system used to design the medium (AGORA, CARVEME, BIGG, etc.)

Run all steps in the notebook and save it. Then add a new entry in the `Available media` section using the following template:

```markdown
---

*Short description of the medium*

[recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/my_recipe.ipynb) |
[medium](https://github.com/micom-dev/media/raw/main/media/my_recipe.qza)

Longer description of the growth medium.
```

Finally create a pull request on this repository which will make your medium for addition into
the repo.

## Available media

**Western diet medium for the human gut (AGORA)**

[recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/agora.ipynb) |
[medium](https://github.com/micom-dev/media/raw/main/media/western_diet_gut_agora.qza)

This is a growth medium representing the likely distribution of available nutrients in the lower intesting under
an average European diet. The medium was taken from https://doi.org/10.1038/nbt.4212 and components commonly
absorbed in the small intestine were diluted 1:10. The medium is adapted to the AGORA database 1.03.

---

**Western diet medium for the human gut (CARVEME)**

[recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/carveme.ipynb) |
[medium](https://github.com/micom-dev/media/raw/main/media/western_diet_gut_carveme.qza)

This is a growth medium representing the likely distribution of available nutrients in the lower intesting under
an average European diet. The medium was taken from https://doi.org/10.1038/nbt.4212 and components commonly
absorbed in the small intestine were diluted 1:10. Only components that could be mapped to the CARVEME DB were kept
and the medium was completed to allow growth for all 1.8K+ genera in the database. The medium is adapted to the CARVEME
reconstructions using Refseq v84.

---

**VMH diets**

| Diet | Recipe | Medium |
| ---- | ------ | ------ |
| Austrian average diet | [Austrian average recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/vmh_eu_average_agora.ipynb) | [Austrian average medium](https://github.com/micom-dev/media/raw/main/media/vmh_eu_average_agora.qza) |
| high fat/protein low carb diet | [high fat low carb recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/vmh_high_fat_low_carb_agora.ipynb) | [high fat low carb medium](https://github.com/micom-dev/media/raw/main/media/vmh_high_fat_low_carb_agora.qza) |
| high fiber diet | [high fiber](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/vmh_high_fiber_carb_agora.ipynb) | [high fiber medium](https://github.com/micom-dev/media/raw/main/media/vmh_high_fiber_agora.qza) |
| fermented foods diet<br> (80% high fiber diet + 20% fermented foods) | [fermented recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/vmh_fermented_agora.ipynb) | [fermented medium](https://github.com/micom-dev/media/raw/main/media/vmh_fermented_agora.qza) |
| baby formula | [formula recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/vmh_formula_agora.ipynb) | [formula medium](https://github.com/micom-dev/media/raw/main/media/vmh_formula_agora.qza) |

These are the completed [VMH](https://vmh.life) growth medium representing a variety of diets. Components
commonly adsorbed in the small intestine were identified by matching reactions to metabolites adsorbed in the
Recon3 human model.

**Provided diets**:
- Austrian average diet
- high fat/protein low carb diet
- high fiber diet
- fermented foods diet (80% high fiber diet + 20% fermented foods)
- baby formula

---

**Breast milk-fed infant (AGORA)**

[recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/breast_milk_agora.ipynb) |
[medium](https://github.com/micom-dev/media/raw/main/media/breast_milk_agora.qza)

This is a completed medium based on a breast milk-only diet of an infant. Lactose is the major carbon source here.
Medium was depleted for components absorbed by human cells and mucin/primary bile acids were added to the medium.

---

**Single meal diets (AGORA)**

| Population | Region | Recipe | Medium |
| ---------- | ------ | ------ | ------ |
| Hadza | Tanzania | [Hadza meal recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/baobab_honey_antelope.ipynb) | [Hadza meal medium](https://github.com/micom-dev/media/raw/main/media/baobab_honey_antelope.qza) |
| Me'Phaa | Mexico | [Me'Phaa recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/guerrero_mountains.ipynb) | [Me'Phaa medium](https://github.com/micom-dev/media/raw/main/media/guerrero_mountains.qza) |
| Chepang | Nepal | [Chepang meal recipe](https://nbviewer.jupyter.org/github/micom-dev/media/blob/main/recipes/himalaya.ipynb) | [Chepang meal medium](https://github.com/micom-dev/media/raw/main/media/himalaya.qza) |

Those are ~1000kcal single meal media for a set of indigenous populations across the globe. Each of them tends to include 4-5 representative food items detailed in the [source mapping](https://github.com/micom-dev/media/raw/main/data/foods_diets.xslx).
Those are not necessarily representative for the diverse diets of the respective poopulation, but are usually more realistic than an average European diet. For a more in depth discussion please refer to
the [2022 ISB Microbiome Series](https://isbscience.org/microbiome2022).
