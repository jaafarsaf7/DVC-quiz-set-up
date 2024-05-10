
# Machine Learning Project with DVC

This repository demonstrates how to use Data Version Control (DVC) in machine learning projects ranging from small to advanced scales, this is a simple example with a sentiment analisis with film reviews. DVC helps in managing data and model versions, streamlining workflows, and improving reproducibility.

## Prerequisites

Before you begin, ensure you have Git installed on your system. You can download it from [git-scm.com](https://git-scm.com/downloads).

## Setting Up DVC

### Installation

#### On macOS

You can install DVC using Homebrew:

```bash
brew install dvc
```

#### On Windows

For Windows, you can use Chocolatey to install DVC:

```bash
choco install dvc
```

#### On Linux

Use pip to install DVC on Linux:

```bash
pip install dvc
```

### Initializing DVC

Navigate to your project directory and run:

```bash
dvc init
```

This command initializes DVC in the directory, creating a `.dvc` folder that stores configuration and data.

### Configuring Remote Storage

DVC supports various types of remote storage. Here's how to set up a remote using Google Drive:

```bash
dvc remote add -d storage gdrive://<your-gdrive-folder-id>
```

Replace `<your-gdrive-folder-id>` with your actual Google Drive folder ID.

### Tracking Data and Models

To start tracking a dataset or model with DVC:

```bash
dvc add data/train.csv
dvc add models/model.joblib
```

This will create `.dvc` files that you should commit to your Git repository:

```bash
git add data/train.csv.dvc models/model.joblib.dvc
git commit -m "Track data and models with DVC"
```

### Pushing Data to Remote Storage

After setting up your remote storage and tracking your files, push them to the remote:

```bash
dvc push
```

### Pulling Data from Remote Storage

To retrieve data from the remote storage:

```bash
dvc pull
```

## Workflow

1. **Modify or add new data/models**: Make changes or add new files.
2. **Run `dvc add`**: Track the new/updated files with DVC.
3. **Commit changes**: Use Git to commit the updated `.dvc` files.
4. **Push changes**: Use `dvc push` to update the remote storage.

## Conclusion

DVC is a powerful tool for machine learning projects, making it easier to handle large datasets and model files, ensuring that every team member has access to the latest versions. For more detailed information, visit the [official DVC documentation](https://dvc.org/doc).
