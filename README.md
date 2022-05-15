# CMS Documentation

This repo contains documentation for the CMS project.

## Installation

### Prerequisites

The installation uses docker. You can check if you have it by running:

`docker --version`

If not, refer to the [Docker installation guide](https://docs.docker.com/engine/install/#server)

Make sure to install Docker Engine, **NOT** Docker Desktop.

### Installation steps

1. Download the database file
```sh
curl -LO https://raw.githubusercontent.com/object-Object-cms/docs/master/data.db
```
2. Pull and start the container
```sh
docker run -it --rm --name cms-instance -p 1234:1234 -v $(pwd)/data.db:/usr/src/app/data.db ghcr.io/object-object-cms/cms-bundle:latest
```

The server should now be running on port 1234, you can proceed to the [Usage guide](USAGE.md)

## Usage

### Sample administrator credentials

These are the credentials of the administrator account in the sample database.

```
Username: admin
Password: admin
```

### Layout editor

The layout editor allows to rearrange blocks, change attributes and customize the page content.
It consists of two sidebars which can be hidden by clicking on the arrows.

The left sidebar is split in half with toolbox on top and component list on the bottom.

The toolbox shows all available components and allows to add them to the page by clicking.

The component list contains all components that are currently on the page and allows to select them by clicking.

The right sidebar is the attribute editor. It allows to modify the currently selected component.

The blocks on the page can be moved by dragging and removed by clicking on the red X button.

After you're done, on the right of the menubar you'll find an accept button. Click it to save changes.

## Management

### Installation

The tkinter management app isn't included in the container. You can download it separately with git.
```sh
git clone https://github.com/object-Object-cms/cms-management
cd cms-management
```

Then install requirements
```sh
pip3 install -U -r requirements.txt
```

Run it with
```sh
python3 admin_manage.py
```

### Usage

After opening the management app, you need to open the database file.

Click on `Open DB` and navigate to the folder where you downloaded the database.
