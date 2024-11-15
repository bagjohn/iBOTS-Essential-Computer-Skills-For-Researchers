
---

# DataLad Workshop: Version Control, Large Files, and GIN Integration

DataLad is a powerful tool that extends Git's capabilities to handle large datasets, making it ideal for research data management. This workshop will guide you through setting up DataLad, managing datasets, handling large files, and integrating with the GIN platform for data sharing and collaboration.

---

## Section 1: Setting Up DataLad

**Introduction:** Before leveraging DataLad's features, it's essential to have it installed and configured properly. This section will guide you through the installation process using Conda and the initial configuration steps.

### Installation Steps

1. **Using Conda:**
   - Open your terminal or command prompt.
   - Create a new Conda environment with DataLad:
     ```bash
     conda create -n datalad_env -c conda-forge datalad
     ```
   - Activate the environment:
     ```bash
     conda activate datalad_env
     ```

### Initial Configuration


**Exercise 1: Verify Installation**

- Activate your Conda environment.
- Run:
  ```bash
  datalad --version
  ```
- Confirm that the installed version is displayed.

---

## Section 2: Creating and Managing Datasets

**Introduction:** DataLad treats datasets as its core units, enabling efficient data management and version control. This section covers creating a dataset, adding data, and understanding dataset structures.

### Creating a Dataset

To create a new dataset:

```bash
datalad create mydataset
```

This command initializes a new dataset in the `mydataset` directory.

### Adding Data to the Dataset

Navigate to your dataset directory and add files:

```bash
cd mydataset
echo "Sample data" > sample.txt
datalad save -m "Added sample.txt"
```

**Exercise 2: Create and Populate a Dataset**

1. Create a dataset named `research_data`.
2. Within this dataset, create a file `notes.txt` containing some text.
3. Save the changes with an appropriate commit message.

---

## Section 3: Handling Large Files with DataLad

**Introduction:** One of DataLad's strengths is its ability to manage large files efficiently using `git-annex`. This section explores how to add large files to your dataset and understand how DataLad handles them.

### Adding Large Files

To add a large file to your dataset:

```bash
datalad add largefile.dat
datalad save -m "Added largefile.dat"
```

DataLad uses `git-annex` to manage large files, keeping your Git history clean and your repository lightweight.

**Exercise 3: Manage a Large File**

1. Within your `research_data` dataset, add a large file: https://uni-bonn.sciebo.de/s/Ntmo3mZdGm2dqRx
2. Use DataLad to add and save this file.

---

## Section 4: Integrating with GIN (G-Node Infrastructure)

**Introduction:** GIN is a platform designed for managing and sharing scientific data, built on Git and `git-annex`. DataLad integrates seamlessly with GIN, allowing you to publish and share your datasets efficiently.

### Prerequisites

1. **Register on GIN:** Create an account at [GIN](https://gin.g-node.org/).

### Publishing a Dataset to GIN

1. **Create a Repository on GIN:**
   - Log in to GIN and create a new repository (e.g., `mydataset`).

2. **Add GIN as a Remote Sibling:**
   - In your dataset directory, run:
     ```bash
     datalad create-sibling-gin -s gin mydataset
     ```
     This command sets up GIN as a remote for your dataset.

3. **Push Data to GIN:**
   - Run:
     ```bash
     datalad push --to gin
     ```
     This command uploads your dataset to GIN.

**Exercise 4: Publish a Dataset to GIN**

1. Set up GIN as a sibling and push your dataset to it.

### Cloning a Dataset from GIN

To clone a dataset from GIN:

```bash
datalad clone https://gin.g-node.org/username/mydataset
```

Replace `username` and `mydataset` with the appropriate values.

**Exercise 5: Clone and Explore a Dataset from GIN**

1. Find a public dataset on GIN.
2. Clone the dataset to your local machine.
3. Navigate through the dataset to understand its structure.
4. Get one of the larger files onto your computer.

---

By completing these sections and exercises, you should have a foundational understanding of DataLad's capabilities in version control, handling large files, and integrating with the GIN platform for data sharing and collaboration. 