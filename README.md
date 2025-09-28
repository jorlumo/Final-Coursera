# Final-Coursera
{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ABZzKX-0NKSH",
        "outputId": "b6f1bdf2-baef-49af-a053-52fa29c93038"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Collecting sqlalchemy==1.3.9\n",
            "  Downloading SQLAlchemy-1.3.9.tar.gz (6.0 MB)\n",
            "\u001b[2K     \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m6.0/6.0 MB\u001b[0m \u001b[31m36.8 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
            "\u001b[?25h  Preparing metadata (setup.py) ... \u001b[?25l\u001b[?25hdone\n",
            "Building wheels for collected packages: sqlalchemy\n",
            "  Building wheel for sqlalchemy (setup.py) ... \u001b[?25l\u001b[?25hdone\n",
            "  Created wheel for sqlalchemy: filename=SQLAlchemy-1.3.9-cp312-cp312-linux_x86_64.whl size=1196048 sha256=c334b7d61b0ac5dfe78b23578c278a96e272608a089e1528ba230e88ee176eb8\n",
            "  Stored in directory: /root/.cache/pip/wheels/b3/1c/42/0e26b8d512adc6bce10ff71a05229366b4ccec641cd3b42111\n",
            "Successfully built sqlalchemy\n",
            "Installing collected packages: sqlalchemy\n",
            "  Attempting uninstall: sqlalchemy\n",
            "    Found existing installation: SQLAlchemy 2.0.43\n",
            "    Uninstalling SQLAlchemy-2.0.43:\n",
            "      Successfully uninstalled SQLAlchemy-2.0.43\n",
            "\u001b[31mERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.\n",
            "ipython-sql 0.5.0 requires sqlalchemy>=2.0, but you have sqlalchemy 1.3.9 which is incompatible.\n",
            "google-adk 1.13.0 requires sqlalchemy<3.0.0,>=2.0, but you have sqlalchemy 1.3.9 which is incompatible.\n",
            "alembic 1.16.5 requires SQLAlchemy>=1.4.0, but you have sqlalchemy 1.3.9 which is incompatible.\n",
            "langchain 0.3.27 requires SQLAlchemy<3,>=1.4, but you have sqlalchemy 1.3.9 which is incompatible.\u001b[0m\u001b[31m\n",
            "\u001b[0mSuccessfully installed sqlalchemy-1.3.9\n"
          ]
        }
      ],
      "source": [
        "!pip install sqlalchemy==1.3.9"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "!pip install ipython-sql\n",
        "!pip install ipython-sql prettytable"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "hpHD1WjONL0t",
        "outputId": "5562629f-0684-4a57-9d1b-7102a6828839"
      },
      "execution_count": 2,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Requirement already satisfied: ipython-sql in /usr/local/lib/python3.12/dist-packages (0.5.0)\n",
            "Requirement already satisfied: prettytable in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (3.16.0)\n",
            "Requirement already satisfied: ipython in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (7.34.0)\n",
            "Collecting sqlalchemy>=2.0 (from ipython-sql)\n",
            "  Downloading sqlalchemy-2.0.43-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (9.6 kB)\n",
            "Requirement already satisfied: sqlparse in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (0.5.3)\n",
            "Requirement already satisfied: six in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (1.17.0)\n",
            "Requirement already satisfied: ipython-genutils in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (0.2.0)\n",
            "Requirement already satisfied: greenlet>=1 in /usr/local/lib/python3.12/dist-packages (from sqlalchemy>=2.0->ipython-sql) (3.2.4)\n",
            "Requirement already satisfied: typing-extensions>=4.6.0 in /usr/local/lib/python3.12/dist-packages (from sqlalchemy>=2.0->ipython-sql) (4.15.0)\n",
            "Requirement already satisfied: setuptools>=18.5 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (75.2.0)\n",
            "Collecting jedi>=0.16 (from ipython->ipython-sql)\n",
            "  Downloading jedi-0.19.2-py2.py3-none-any.whl.metadata (22 kB)\n",
            "Requirement already satisfied: decorator in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (4.4.2)\n",
            "Requirement already satisfied: pickleshare in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.7.5)\n",
            "Requirement already satisfied: traitlets>=4.2 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (5.7.1)\n",
            "Requirement already satisfied: prompt-toolkit!=3.0.0,!=3.0.1,<3.1.0,>=2.0.0 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (3.0.52)\n",
            "Requirement already satisfied: pygments in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (2.19.2)\n",
            "Requirement already satisfied: backcall in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.2.0)\n",
            "Requirement already satisfied: matplotlib-inline in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.1.7)\n",
            "Requirement already satisfied: pexpect>4.3 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (4.9.0)\n",
            "Requirement already satisfied: wcwidth in /usr/local/lib/python3.12/dist-packages (from prettytable->ipython-sql) (0.2.13)\n",
            "Requirement already satisfied: parso<0.9.0,>=0.8.4 in /usr/local/lib/python3.12/dist-packages (from jedi>=0.16->ipython->ipython-sql) (0.8.5)\n",
            "Requirement already satisfied: ptyprocess>=0.5 in /usr/local/lib/python3.12/dist-packages (from pexpect>4.3->ipython->ipython-sql) (0.7.0)\n",
            "Downloading sqlalchemy-2.0.43-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (3.3 MB)\n",
            "\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m3.3/3.3 MB\u001b[0m \u001b[31m26.6 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
            "\u001b[?25hDownloading jedi-0.19.2-py2.py3-none-any.whl (1.6 MB)\n",
            "\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m1.6/1.6 MB\u001b[0m \u001b[31m58.7 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
            "\u001b[?25hInstalling collected packages: sqlalchemy, jedi\n",
            "  Attempting uninstall: sqlalchemy\n",
            "    Found existing installation: SQLAlchemy 1.3.9\n",
            "    Uninstalling SQLAlchemy-1.3.9:\n",
            "      Successfully uninstalled SQLAlchemy-1.3.9\n",
            "Successfully installed jedi-0.19.2 sqlalchemy-2.0.43\n",
            "Requirement already satisfied: ipython-sql in /usr/local/lib/python3.12/dist-packages (0.5.0)\n",
            "Requirement already satisfied: prettytable in /usr/local/lib/python3.12/dist-packages (3.16.0)\n",
            "Requirement already satisfied: ipython in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (7.34.0)\n",
            "Requirement already satisfied: sqlalchemy>=2.0 in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (2.0.43)\n",
            "Requirement already satisfied: sqlparse in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (0.5.3)\n",
            "Requirement already satisfied: six in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (1.17.0)\n",
            "Requirement already satisfied: ipython-genutils in /usr/local/lib/python3.12/dist-packages (from ipython-sql) (0.2.0)\n",
            "Requirement already satisfied: wcwidth in /usr/local/lib/python3.12/dist-packages (from prettytable) (0.2.13)\n",
            "Requirement already satisfied: greenlet>=1 in /usr/local/lib/python3.12/dist-packages (from sqlalchemy>=2.0->ipython-sql) (3.2.4)\n",
            "Requirement already satisfied: typing-extensions>=4.6.0 in /usr/local/lib/python3.12/dist-packages (from sqlalchemy>=2.0->ipython-sql) (4.15.0)\n",
            "Requirement already satisfied: setuptools>=18.5 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (75.2.0)\n",
            "Requirement already satisfied: jedi>=0.16 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.19.2)\n",
            "Requirement already satisfied: decorator in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (4.4.2)\n",
            "Requirement already satisfied: pickleshare in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.7.5)\n",
            "Requirement already satisfied: traitlets>=4.2 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (5.7.1)\n",
            "Requirement already satisfied: prompt-toolkit!=3.0.0,!=3.0.1,<3.1.0,>=2.0.0 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (3.0.52)\n",
            "Requirement already satisfied: pygments in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (2.19.2)\n",
            "Requirement already satisfied: backcall in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.2.0)\n",
            "Requirement already satisfied: matplotlib-inline in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (0.1.7)\n",
            "Requirement already satisfied: pexpect>4.3 in /usr/local/lib/python3.12/dist-packages (from ipython->ipython-sql) (4.9.0)\n",
            "Requirement already satisfied: parso<0.9.0,>=0.8.4 in /usr/local/lib/python3.12/dist-packages (from jedi>=0.16->ipython->ipython-sql) (0.8.5)\n",
            "Requirement already satisfied: ptyprocess>=0.5 in /usr/local/lib/python3.12/dist-packages (from pexpect>4.3->ipython->ipython-sql) (0.7.0)\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%load_ext sql"
      ],
      "metadata": {
        "id": "5e-7L8A2NXMr"
      },
      "execution_count": 3,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import csv, sqlite3\n",
        "import prettytable\n",
        "prettytable.DEFAULT = 'DEFAULT'\n",
        "\n",
        "con = sqlite3.connect(\"my_data1.db\")\n",
        "cur = con.cursor()"
      ],
      "metadata": {
        "id": "WtJBFjYINgNj"
      },
      "execution_count": 4,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "!pip install -q pandas"
      ],
      "metadata": {
        "id": "7hOqd6j0NniL"
      },
      "execution_count": 5,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "%sql sqlite:///my_data1.db"
      ],
      "metadata": {
        "id": "R0Q_yR48NrmT"
      },
      "execution_count": 6,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv(\"https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/labs/module_2/data/Spacex.csv\")\n",
        "df.to_sql(\"SPACEXTBL\", con, if_exists='replace', index=False,method=\"multi\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "knBA6duUN_Lr",
        "outputId": "4fc81c56-e057-4a80-e55c-692c62d6c6b2"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "101"
            ]
          },
          "metadata": {},
          "execution_count": 7
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "#DROP THE TABLE IF EXISTS"
      ],
      "metadata": {
        "id": "nBWNCj94OSNP"
      },
      "execution_count": 8,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "%sql DROP TABLE IF EXISTS SPACEXTABLE;"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "DHF4iq8sOZ4j",
        "outputId": "68d24009-4114-4999-a5d6-ffd7b880d004"
      },
      "execution_count": 9,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            " * sqlite:///my_data1.db\n",
            "Done.\n"
          ]
        },
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "[]"
            ]
          },
          "metadata": {},
          "execution_count": 9
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%sql create table SPACEXTABLE as select * from SPACEXTBL where Date is not null"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "5v4nGjY3Ocok",
        "outputId": "f60499ae-ec45-4bab-a93c-115a8dff74da"
      },
      "execution_count": 10,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            " * sqlite:///my_data1.db\n",
            "Done.\n"
          ]
        },
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "[]"
            ]
          },
          "metadata": {},
          "execution_count": 10
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Assuming your dataframe is named 'df'\n",
        "unique_sites = df['Launch_Site'].unique()\n",
        "print(unique_sites)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ZspdA8_bOfrD",
        "outputId": "86f4dcfb-d207-4b3b-fc2b-dc2009c14335"
      },
      "execution_count": 12,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "['CCAFS LC-40' 'VAFB SLC-4E' 'KSC LC-39A' 'CCAFS SLC-40']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "unique_sites = df['Launch_Site'].unique().tolist()\n",
        "unique_sites"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "7fPHgjJGO3Bj",
        "outputId": "c34d7cdf-6a47-4a80-9c90-480db15000c8"
      },
      "execution_count": 14,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "['CCAFS LC-40', 'VAFB SLC-4E', 'KSC LC-39A', 'CCAFS SLC-40']"
            ]
          },
          "metadata": {},
          "execution_count": 14
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Filter rows where LaunchSite starts with 'CCA' and display 5 records\n",
        "df[df['Launch_Site'].str.startswith('CCA')].head(5)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 206
        },
        "id": "CvGEf3mNPkB8",
        "outputId": "17b34905-f1c2-4f79-86fc-3e86637714aa"
      },
      "execution_count": 16,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "         Date Time (UTC) Booster_Version  Launch_Site  \\\n",
              "0  2010-06-04   18:45:00  F9 v1.0  B0003  CCAFS LC-40   \n",
              "1  2010-12-08   15:43:00  F9 v1.0  B0004  CCAFS LC-40   \n",
              "2  2012-05-22    7:44:00  F9 v1.0  B0005  CCAFS LC-40   \n",
              "3  2012-10-08    0:35:00  F9 v1.0  B0006  CCAFS LC-40   \n",
              "4  2013-03-01   15:10:00  F9 v1.0  B0007  CCAFS LC-40   \n",
              "\n",
              "                                             Payload  PAYLOAD_MASS__KG_  \\\n",
              "0               Dragon Spacecraft Qualification Unit                  0   \n",
              "1  Dragon demo flight C1, two CubeSats, barrel of...                  0   \n",
              "2                              Dragon demo flight C2                525   \n",
              "3                                       SpaceX CRS-1                500   \n",
              "4                                       SpaceX CRS-2                677   \n",
              "\n",
              "       Orbit         Customer Mission_Outcome      Landing_Outcome  \n",
              "0        LEO           SpaceX         Success  Failure (parachute)  \n",
              "1  LEO (ISS)  NASA (COTS) NRO         Success  Failure (parachute)  \n",
              "2  LEO (ISS)      NASA (COTS)         Success           No attempt  \n",
              "3  LEO (ISS)       NASA (CRS)         Success           No attempt  \n",
              "4  LEO (ISS)       NASA (CRS)         Success           No attempt  "
            ],
            "text/html": [
              "\n",
              "  <div id=\"df-a15f31fb-812c-4133-b165-afcc29d0f08b\" class=\"colab-df-container\">\n",
              "    <div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Date</th>\n",
              "      <th>Time (UTC)</th>\n",
              "      <th>Booster_Version</th>\n",
              "      <th>Launch_Site</th>\n",
              "      <th>Payload</th>\n",
              "      <th>PAYLOAD_MASS__KG_</th>\n",
              "      <th>Orbit</th>\n",
              "      <th>Customer</th>\n",
              "      <th>Mission_Outcome</th>\n",
              "      <th>Landing_Outcome</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>2010-06-04</td>\n",
              "      <td>18:45:00</td>\n",
              "      <td>F9 v1.0  B0003</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>Dragon Spacecraft Qualification Unit</td>\n",
              "      <td>0</td>\n",
              "      <td>LEO</td>\n",
              "      <td>SpaceX</td>\n",
              "      <td>Success</td>\n",
              "      <td>Failure (parachute)</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>2010-12-08</td>\n",
              "      <td>15:43:00</td>\n",
              "      <td>F9 v1.0  B0004</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>Dragon demo flight C1, two CubeSats, barrel of...</td>\n",
              "      <td>0</td>\n",
              "      <td>LEO (ISS)</td>\n",
              "      <td>NASA (COTS) NRO</td>\n",
              "      <td>Success</td>\n",
              "      <td>Failure (parachute)</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>2012-05-22</td>\n",
              "      <td>7:44:00</td>\n",
              "      <td>F9 v1.0  B0005</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>Dragon demo flight C2</td>\n",
              "      <td>525</td>\n",
              "      <td>LEO (ISS)</td>\n",
              "      <td>NASA (COTS)</td>\n",
              "      <td>Success</td>\n",
              "      <td>No attempt</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>2012-10-08</td>\n",
              "      <td>0:35:00</td>\n",
              "      <td>F9 v1.0  B0006</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>SpaceX CRS-1</td>\n",
              "      <td>500</td>\n",
              "      <td>LEO (ISS)</td>\n",
              "      <td>NASA (CRS)</td>\n",
              "      <td>Success</td>\n",
              "      <td>No attempt</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>2013-03-01</td>\n",
              "      <td>15:10:00</td>\n",
              "      <td>F9 v1.0  B0007</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>SpaceX CRS-2</td>\n",
              "      <td>677</td>\n",
              "      <td>LEO (ISS)</td>\n",
              "      <td>NASA (CRS)</td>\n",
              "      <td>Success</td>\n",
              "      <td>No attempt</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>\n",
              "    <div class=\"colab-df-buttons\">\n",
              "\n",
              "  <div class=\"colab-df-container\">\n",
              "    <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-a15f31fb-812c-4133-b165-afcc29d0f08b')\"\n",
              "            title=\"Convert this dataframe to an interactive table.\"\n",
              "            style=\"display:none;\">\n",
              "\n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\" viewBox=\"0 -960 960 960\">\n",
              "    <path d=\"M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z\"/>\n",
              "  </svg>\n",
              "    </button>\n",
              "\n",
              "  <style>\n",
              "    .colab-df-container {\n",
              "      display:flex;\n",
              "      gap: 12px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert {\n",
              "      background-color: #E8F0FE;\n",
              "      border: none;\n",
              "      border-radius: 50%;\n",
              "      cursor: pointer;\n",
              "      display: none;\n",
              "      fill: #1967D2;\n",
              "      height: 32px;\n",
              "      padding: 0 0 0 0;\n",
              "      width: 32px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert:hover {\n",
              "      background-color: #E2EBFA;\n",
              "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "      fill: #174EA6;\n",
              "    }\n",
              "\n",
              "    .colab-df-buttons div {\n",
              "      margin-bottom: 4px;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert {\n",
              "      background-color: #3B4455;\n",
              "      fill: #D2E3FC;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert:hover {\n",
              "      background-color: #434B5C;\n",
              "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "      fill: #FFFFFF;\n",
              "    }\n",
              "  </style>\n",
              "\n",
              "    <script>\n",
              "      const buttonEl =\n",
              "        document.querySelector('#df-a15f31fb-812c-4133-b165-afcc29d0f08b button.colab-df-convert');\n",
              "      buttonEl.style.display =\n",
              "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "      async function convertToInteractive(key) {\n",
              "        const element = document.querySelector('#df-a15f31fb-812c-4133-b165-afcc29d0f08b');\n",
              "        const dataTable =\n",
              "          await google.colab.kernel.invokeFunction('convertToInteractive',\n",
              "                                                    [key], {});\n",
              "        if (!dataTable) return;\n",
              "\n",
              "        const docLinkHtml = 'Like what you see? Visit the ' +\n",
              "          '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
              "          + ' to learn more about interactive tables.';\n",
              "        element.innerHTML = '';\n",
              "        dataTable['output_type'] = 'display_data';\n",
              "        await google.colab.output.renderOutput(dataTable, element);\n",
              "        const docLink = document.createElement('div');\n",
              "        docLink.innerHTML = docLinkHtml;\n",
              "        element.appendChild(docLink);\n",
              "      }\n",
              "    </script>\n",
              "  </div>\n",
              "\n",
              "\n",
              "    <div id=\"df-dd42bc9b-3581-4339-9521-713531335438\">\n",
              "      <button class=\"colab-df-quickchart\" onclick=\"quickchart('df-dd42bc9b-3581-4339-9521-713531335438')\"\n",
              "                title=\"Suggest charts\"\n",
              "                style=\"display:none;\">\n",
              "\n",
              "<svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "     width=\"24px\">\n",
              "    <g>\n",
              "        <path d=\"M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z\"/>\n",
              "    </g>\n",
              "</svg>\n",
              "      </button>\n",
              "\n",
              "<style>\n",
              "  .colab-df-quickchart {\n",
              "      --bg-color: #E8F0FE;\n",
              "      --fill-color: #1967D2;\n",
              "      --hover-bg-color: #E2EBFA;\n",
              "      --hover-fill-color: #174EA6;\n",
              "      --disabled-fill-color: #AAA;\n",
              "      --disabled-bg-color: #DDD;\n",
              "  }\n",
              "\n",
              "  [theme=dark] .colab-df-quickchart {\n",
              "      --bg-color: #3B4455;\n",
              "      --fill-color: #D2E3FC;\n",
              "      --hover-bg-color: #434B5C;\n",
              "      --hover-fill-color: #FFFFFF;\n",
              "      --disabled-bg-color: #3B4455;\n",
              "      --disabled-fill-color: #666;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart {\n",
              "    background-color: var(--bg-color);\n",
              "    border: none;\n",
              "    border-radius: 50%;\n",
              "    cursor: pointer;\n",
              "    display: none;\n",
              "    fill: var(--fill-color);\n",
              "    height: 32px;\n",
              "    padding: 0;\n",
              "    width: 32px;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart:hover {\n",
              "    background-color: var(--hover-bg-color);\n",
              "    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "    fill: var(--button-hover-fill-color);\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart-complete:disabled,\n",
              "  .colab-df-quickchart-complete:disabled:hover {\n",
              "    background-color: var(--disabled-bg-color);\n",
              "    fill: var(--disabled-fill-color);\n",
              "    box-shadow: none;\n",
              "  }\n",
              "\n",
              "  .colab-df-spinner {\n",
              "    border: 2px solid var(--fill-color);\n",
              "    border-color: transparent;\n",
              "    border-bottom-color: var(--fill-color);\n",
              "    animation:\n",
              "      spin 1s steps(1) infinite;\n",
              "  }\n",
              "\n",
              "  @keyframes spin {\n",
              "    0% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "      border-left-color: var(--fill-color);\n",
              "    }\n",
              "    20% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    30% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    40% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    60% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    80% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "    90% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "  }\n",
              "</style>\n",
              "\n",
              "      <script>\n",
              "        async function quickchart(key) {\n",
              "          const quickchartButtonEl =\n",
              "            document.querySelector('#' + key + ' button');\n",
              "          quickchartButtonEl.disabled = true;  // To prevent multiple clicks.\n",
              "          quickchartButtonEl.classList.add('colab-df-spinner');\n",
              "          try {\n",
              "            const charts = await google.colab.kernel.invokeFunction(\n",
              "                'suggestCharts', [key], {});\n",
              "          } catch (error) {\n",
              "            console.error('Error during call to suggestCharts:', error);\n",
              "          }\n",
              "          quickchartButtonEl.classList.remove('colab-df-spinner');\n",
              "          quickchartButtonEl.classList.add('colab-df-quickchart-complete');\n",
              "        }\n",
              "        (() => {\n",
              "          let quickchartButtonEl =\n",
              "            document.querySelector('#df-dd42bc9b-3581-4339-9521-713531335438 button');\n",
              "          quickchartButtonEl.style.display =\n",
              "            google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "        })();\n",
              "      </script>\n",
              "    </div>\n",
              "\n",
              "    </div>\n",
              "  </div>\n"
            ],
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "dataframe",
              "summary": "{\n  \"name\": \"df[df['Launch_Site']\",\n  \"rows\": 5,\n  \"fields\": [\n    {\n      \"column\": \"Date\",\n      \"properties\": {\n        \"dtype\": \"object\",\n        \"num_unique_values\": 5,\n        \"samples\": [\n          \"2010-12-08\",\n          \"2013-03-01\",\n          \"2012-05-22\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Time (UTC)\",\n      \"properties\": {\n        \"dtype\": \"object\",\n        \"num_unique_values\": 5,\n        \"samples\": [\n          \"15:43:00\",\n          \"15:10:00\",\n          \"7:44:00\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Booster_Version\",\n      \"properties\": {\n        \"dtype\": \"string\",\n        \"num_unique_values\": 5,\n        \"samples\": [\n          \"F9 v1.0  B0004\",\n          \"F9 v1.0  B0007\",\n          \"F9 v1.0  B0005\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Launch_Site\",\n      \"properties\": {\n        \"dtype\": \"category\",\n        \"num_unique_values\": 1,\n        \"samples\": [\n          \"CCAFS LC-40\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Payload\",\n      \"properties\": {\n        \"dtype\": \"string\",\n        \"num_unique_values\": 5,\n        \"samples\": [\n          \"Dragon demo flight C1, two CubeSats, barrel of Brouere cheese\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"PAYLOAD_MASS__KG_\",\n      \"properties\": {\n        \"dtype\": \"number\",\n        \"std\": 318,\n        \"min\": 0,\n        \"max\": 677,\n        \"num_unique_values\": 4,\n        \"samples\": [\n          525\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Orbit\",\n      \"properties\": {\n        \"dtype\": \"category\",\n        \"num_unique_values\": 2,\n        \"samples\": [\n          \"LEO (ISS)\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Customer\",\n      \"properties\": {\n        \"dtype\": \"string\",\n        \"num_unique_values\": 4,\n        \"samples\": [\n          \"NASA (COTS) NRO\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Mission_Outcome\",\n      \"properties\": {\n        \"dtype\": \"category\",\n        \"num_unique_values\": 1,\n        \"samples\": [\n          \"Success\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Landing_Outcome\",\n      \"properties\": {\n        \"dtype\": \"category\",\n        \"num_unique_values\": 2,\n        \"samples\": [\n          \"No attempt\"\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    }\n  ]\n}"
            }
          },
          "metadata": {},
          "execution_count": 16
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Filter for NASA (CRS) missions and sum payload mass\n",
        "total_payload = df[df['Customer'] == 'NASA (CRS)']['PAYLOAD_MASS__KG_'].sum()\n",
        "print(\"Total payload mass carried by NASA (CRS) boosters:\", total_payload)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "AIxAvqqkPvom",
        "outputId": "005f0e6b-92ba-440c-97b8-48cc8a831351"
      },
      "execution_count": 18,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Total payload mass carried by NASA (CRS) boosters: 45596\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Filter for booster version F9 v1.1 and calculate average payload\n",
        "avg_payload = df[df['Booster_Version'] == 'F9 v1.1']['PAYLOAD_MASS__KG_'].mean()\n",
        "print(\"Average payload mass for F9 v1.1 boosters:\", avg_payload)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "pQPBB6hAQtd0",
        "outputId": "8192bd17-ac83-4ed8-9139-81d03c7db43f"
      },
      "execution_count": 20,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Average payload mass for F9 v1.1 boosters: 2928.4\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Filter for successful ground pad landings\n",
        "first_ground_pad = df[df['Landing_Outcome'] == 'Success (ground pad)']\n",
        "\n",
        "# Get the earliest date\n",
        "first_date = first_ground_pad['Date'].min()\n",
        "print(\"First successful ground pad landing date:\", first_date)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "7iw4jQwIRFak",
        "outputId": "6c1cbffb-7b00-4fe1-b573-6e19a3dc628d"
      },
      "execution_count": 22,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "First successful ground pad landing date: 2015-12-22\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "LandingOutcome == \"Success (drone ship)\"\n",
        "\n",
        "PayloadMass > 4000\n",
        "\n",
        "PayloadMass < 6000"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 222
        },
        "id": "-8Xo4co3Rgsc",
        "outputId": "948715c1-217a-4131-fe79-e91e705057cf"
      },
      "execution_count": 23,
      "outputs": [
        {
          "output_type": "error",
          "ename": "NameError",
          "evalue": "name 'LandingOutcome' is not defined",
          "traceback": [
            "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
            "\u001b[0;31mNameError\u001b[0m                                 Traceback (most recent call last)",
            "\u001b[0;32m/tmp/ipython-input-1881781006.py\u001b[0m in \u001b[0;36m<cell line: 0>\u001b[0;34m()\u001b[0m\n\u001b[0;32m----> 1\u001b[0;31m \u001b[0mLandingOutcome\u001b[0m \u001b[0;34m==\u001b[0m \u001b[0;34m\"Success (drone ship)\"\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      2\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      3\u001b[0m \u001b[0mPayloadMass\u001b[0m \u001b[0;34m>\u001b[0m \u001b[0;36m4000\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      4\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      5\u001b[0m \u001b[0mPayloadMass\u001b[0m \u001b[0;34m<\u001b[0m \u001b[0;36m6000\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;31mNameError\u001b[0m: name 'LandingOutcome' is not defined"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "abdd70c9"
      },
      "source": [
        "The previous cell had a `NameError` because `LandingOutcome` and `PayloadMass` were not defined. To filter the DataFrame `df`, you need to specify the DataFrame and the column name, like `df['Landing_Outcome']` and `df['PAYLOAD_MASS__KG_']`.\n",
        "\n",
        "Here's the corrected code to filter the DataFrame:"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 175
        },
        "id": "0c23e9de",
        "outputId": "e7bee679-aaf1-4eb0-e816-c896077ec527"
      },
      "source": [
        "filtered_df = df[(df['Landing_Outcome'] == 'Success (drone ship)') & (df['PAYLOAD_MASS__KG_'] > 4000) & (df['PAYLOAD_MASS__KG_'] < 6000)]\n",
        "display(filtered_df)"
      ],
      "execution_count": 24,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "          Date Time (UTC) Booster_Version  Launch_Site                Payload  \\\n",
              "23  2016-05-06    5:21:00     F9 FT B1022  CCAFS LC-40               JCSAT-14   \n",
              "27  2016-08-14    5:26:00     F9 FT B1026  CCAFS LC-40               JCSAT-16   \n",
              "31  2017-03-30   22:27:00  F9 FT  B1021.2   KSC LC-39A                 SES-10   \n",
              "42  2017-10-11   22:53:00  F9 FT  B1031.2   KSC LC-39A  SES-11 / EchoStar 105   \n",
              "\n",
              "    PAYLOAD_MASS__KG_ Orbit                Customer Mission_Outcome  \\\n",
              "23               4696   GTO  SKY Perfect JSAT Group         Success   \n",
              "27               4600   GTO  SKY Perfect JSAT Group         Success   \n",
              "31               5300   GTO                     SES         Success   \n",
              "42               5200   GTO            SES EchoStar         Success   \n",
              "\n",
              "         Landing_Outcome  \n",
              "23  Success (drone ship)  \n",
              "27  Success (drone ship)  \n",
              "31  Success (drone ship)  \n",
              "42  Success (drone ship)  "
            ],
            "text/html": [
              "\n",
              "  <div id=\"df-d80ce0bb-1451-4f9d-bb12-628e3a595735\" class=\"colab-df-container\">\n",
              "    <div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Date</th>\n",
              "      <th>Time (UTC)</th>\n",
              "      <th>Booster_Version</th>\n",
              "      <th>Launch_Site</th>\n",
              "      <th>Payload</th>\n",
              "      <th>PAYLOAD_MASS__KG_</th>\n",
              "      <th>Orbit</th>\n",
              "      <th>Customer</th>\n",
              "      <th>Mission_Outcome</th>\n",
              "      <th>Landing_Outcome</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>23</th>\n",
              "      <td>2016-05-06</td>\n",
              "      <td>5:21:00</td>\n",
              "      <td>F9 FT B1022</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>JCSAT-14</td>\n",
              "      <td>4696</td>\n",
              "      <td>GTO</td>\n",
              "      <td>SKY Perfect JSAT Group</td>\n",
              "      <td>Success</td>\n",
              "      <td>Success (drone ship)</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>27</th>\n",
              "      <td>2016-08-14</td>\n",
              "      <td>5:26:00</td>\n",
              "      <td>F9 FT B1026</td>\n",
              "      <td>CCAFS LC-40</td>\n",
              "      <td>JCSAT-16</td>\n",
              "      <td>4600</td>\n",
              "      <td>GTO</td>\n",
              "      <td>SKY Perfect JSAT Group</td>\n",
              "      <td>Success</td>\n",
              "      <td>Success (drone ship)</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>31</th>\n",
              "      <td>2017-03-30</td>\n",
              "      <td>22:27:00</td>\n",
              "      <td>F9 FT  B1021.2</td>\n",
              "      <td>KSC LC-39A</td>\n",
              "      <td>SES-10</td>\n",
              "      <td>5300</td>\n",
              "      <td>GTO</td>\n",
              "      <td>SES</td>\n",
              "      <td>Success</td>\n",
              "      <td>Success (drone ship)</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>42</th>\n",
              "      <td>2017-10-11</td>\n",
              "      <td>22:53:00</td>\n",
              "      <td>F9 FT  B1031.2</td>\n",
              "      <td>KSC LC-39A</td>\n",
              "      <td>SES-11 / EchoStar 105</td>\n",
              "      <td>5200</td>\n",
              "      <td>GTO</td>\n",
              "      <td>SES EchoStar</td>\n",
              "      <td>Success</td>\n",
              "      <td>Success (drone ship)</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>\n",
              "    <div class=\"colab-df-buttons\">\n",
              "\n",
              "  <div class=\"colab-df-container\">\n",
              "    <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-d80ce0bb-1451-4f9d-bb12-628e3a595735')\"\n",
              "            title=\"Convert this dataframe to an interactive table.\"\n",
              "            style=\"display:none;\">\n",
              "\n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\" viewBox=\"0 -960 960 960\">\n",
              "    <path d=\"M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z\"/>\n",
              "  </svg>\n",
              "    </button>\n",
              "\n",
              "  <style>\n",
              "    .colab-df-container {\n",
              "      display:flex;\n",
              "      gap: 12px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert {\n",
              "      background-color: #E8F0FE;\n",
              "      border: none;\n",
              "      border-radius: 50%;\n",
              "      cursor: pointer;\n",
              "      display: none;\n",
              "      fill: #1967D2;\n",
              "      height: 32px;\n",
              "      padding: 0 0 0 0;\n",
              "      width: 32px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert:hover {\n",
              "      background-color: #E2EBFA;\n",
              "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "      fill: #174EA6;\n",
              "    }\n",
              "\n",
              "    .colab-df-buttons div {\n",
              "      margin-bottom: 4px;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert {\n",
              "      background-color: #3B4455;\n",
              "      fill: #D2E3FC;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert:hover {\n",
              "      background-color: #434B5C;\n",
              "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "      fill: #FFFFFF;\n",
              "    }\n",
              "  </style>\n",
              "\n",
              "    <script>\n",
              "      const buttonEl =\n",
              "        document.querySelector('#df-d80ce0bb-1451-4f9d-bb12-628e3a595735 button.colab-df-convert');\n",
              "      buttonEl.style.display =\n",
              "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "      async function convertToInteractive(key) {\n",
              "        const element = document.querySelector('#df-d80ce0bb-1451-4f9d-bb12-628e3a595735');\n",
              "        const dataTable =\n",
              "          await google.colab.kernel.invokeFunction('convertToInteractive',\n",
              "                                                    [key], {});\n",
              "        if (!dataTable) return;\n",
              "\n",
              "        const docLinkHtml = 'Like what you see? Visit the ' +\n",
              "          '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
              "          + ' to learn more about interactive tables.';\n",
              "        element.innerHTML = '';\n",
              "        dataTable['output_type'] = 'display_data';\n",
              "        await google.colab.output.renderOutput(dataTable, element);\n",
              "        const docLink = document.createElement('div');\n",
              "        docLink.innerHTML = docLinkHtml;\n",
              "        element.appendChild(docLink);\n",
              "      }\n",
              "    </script>\n",
              "  </div>\n",
              "\n",
              "\n",
              "    <div id=\"df-c4cab039-412a-45a3-acf3-4daa5fe37fc9\">\n",
              "      <button class=\"colab-df-quickchart\" onclick=\"quickchart('df-c4cab039-412a-45a3-acf3-4daa5fe37fc9')\"\n",
              "                title=\"Suggest charts\"\n",
              "                style=\"display:none;\">\n",
              "\n",
              "<svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "     width=\"24px\">\n",
              "    <g>\n",
              "        <path d=\"M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z\"/>\n",
              "    </g>\n",
              "</svg>\n",
              "      </button>\n",
              "\n",
              "<style>\n",
              "  .colab-df-quickchart {\n",
              "      --bg-color: #E8F0FE;\n",
              "      --fill-color: #1967D2;\n",
              "      --hover-bg-color: #E2EBFA;\n",
              "      --hover-fill-color: #174EA6;\n",
              "      --disabled-fill-color: #AAA;\n",
              "      --disabled-bg-color: #DDD;\n",
              "  }\n",
              "\n",
              "  [theme=dark] .colab-df-quickchart {\n",
              "      --bg-color: #3B4455;\n",
              "      --fill-color: #D2E3FC;\n",
              "      --hover-bg-color: #434B5C;\n",
              "      --hover-fill-color: #FFFFFF;\n",
              "      --disabled-bg-color: #3B4455;\n",
              "      --disabled-fill-color: #666;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart {\n",
              "    background-color: var(--bg-color);\n",
              "    border: none;\n",
              "    border-radius: 50%;\n",
              "    cursor: pointer;\n",
              "    display: none;\n",
              "    fill: var(--fill-color);\n",
              "    height: 32px;\n",
              "    padding: 0;\n",
              "    width: 32px;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart:hover {\n",
              "    background-color: var(--hover-bg-color);\n",
              "    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "    fill: var(--button-hover-fill-color);\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart-complete:disabled,\n",
              "  .colab-df-quickchart-complete:disabled:hover {\n",
              "    background-color: var(--disabled-bg-color);\n",
              "    fill: var(--disabled-fill-color);\n",
              "    box-shadow: none;\n",
              "  }\n",
              "\n",
              "  .colab-df-spinner {\n",
              "    border: 2px solid var(--fill-color);\n",
              "    border-color: transparent;\n",
              "    border-bottom-color: var(--fill-color);\n",
              "    animation:\n",
              "      spin 1s steps(1) infinite;\n",
              "  }\n",
              "\n",
              "  @keyframes spin {\n",
              "    0% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "      border-left-color: var(--fill-color);\n",
              "    }\n",
              "    20% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    30% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    40% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    60% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    80% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "    90% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "  }\n",
              "</style>\n",
              "\n",
              "      <script>\n",
              "        async function quickchart(key) {\n",
              "          const quickchartButtonEl =\n",
              "            document.querySelector('#' + key + ' button');\n",
              "          quickchartButtonEl.disabled = true;  // To prevent multiple clicks.\n",
              "          quickchartButtonEl.classList.add('colab-df-spinner');\n",
              "          try {\n",
              "            const charts = await google.colab.kernel.invokeFunction(\n",
              "                'suggestCharts', [key], {});\n",
              "          } catch (error) {\n",
              "            console.error('Error during call to suggestCharts:', error);\n",
              "          }\n",
              "          quickchartButtonEl.classList.remove('colab-df-spinner');\n",
              "          quickchartButtonEl.classList.add('colab-df-quickchart-complete');\n",
              "        }\n",
              "        (() => {\n",
              "          let quickchartButtonEl =\n",
              "            document.querySelector('#df-c4cab039-412a-45a3-acf3-4daa5fe37fc9 button');\n",
              "          quickchartButtonEl.style.display =\n",
              "            google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "        })();\n",
              "      </script>\n",
              "    </div>\n",
              "\n",
              "  <div id=\"id_db7351b5-3a8d-4422-9c77-1b2ca72dbd2e\">\n",
              "    <style>\n",
              "      .colab-df-generate {\n",
              "        background-color: #E8F0FE;\n",
              "        border: none;\n",
              "        border-radius: 50%;\n",
              "        cursor: pointer;\n",
              "        display: none;\n",
              "        fill: #1967D2;\n",
              "        height: 32px;\n",
              "        padding: 0 0 0 0;\n",
              "        width: 32px;\n",
              "      }\n",
              "\n",
              "      .colab-df-generate:hover {\n",
              "        background-color: #E2EBFA;\n",
              "        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "        fill: #174EA6;\n",
              "      }\n",
              "\n",
              "      [theme=dark] .colab-df-generate {\n",
              "        background-color: #3B4455;\n",
              "        fill: #D2E3FC;\n",
              "      }\n",
              "\n",
              "      [theme=dark] .colab-df-generate:hover {\n",
              "        background-color: #434B5C;\n",
              "        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "        fill: #FFFFFF;\n",
              "      }\n",
              "    </style>\n",
              "    <button class=\"colab-df-generate\" onclick=\"generateWithVariable('filtered_df')\"\n",
              "            title=\"Generate code using this dataframe.\"\n",
              "            style=\"display:none;\">\n",
              "\n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "       width=\"24px\">\n",
              "    <path d=\"M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z\"/>\n",
              "  </svg>\n",
              "    </button>\n",
              "    <script>\n",
              "      (() => {\n",
              "      const buttonEl =\n",
              "        document.querySelector('#id_db7351b5-3a8d-4422-9c77-1b2ca72dbd2e button.colab-df-generate');\n",
              "      buttonEl.style.display =\n",
              "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "      buttonEl.onclick = () => {\n",
              "        google.colab.notebook.generateWithVariable('filtered_df');\n",
              "      }\n",
              "      })();\n",
              "    </script>\n",
              "  </div>\n",
              "\n",
              "    </div>\n",
              "  </div>\n"
            ],
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "dataframe",
              "variable_name": "filtered_df",
              "repr_error": "0"
            }
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Filter conditions\n",
        "filtered = df[\n",
        "    (df['Landing_Outcome'] == 'Success (drone ship)') &\n",
        "    (df['PAYLOAD_MASS__KG_'] > 4000) &\n",
        "    (df['PAYLOAD_MASS__KG_'] < 6000)\n",
        "]\n",
        "\n",
        "# List unique booster names\n",
        "boosters = filtered['Booster_Version'].unique()\n",
        "print(\"Boosters with successful drone ship landing and payload 4000–6000 kg:\")\n",
        "print(boosters)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "F1z0b552SK6V",
        "outputId": "0ee9e4ab-254f-4207-8262-d51b18a878f6"
      },
      "execution_count": 26,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Boosters with successful drone ship landing and payload 4000–6000 kg:\n",
            "['F9 FT B1022' 'F9 FT B1026' 'F9 FT  B1021.2' 'F9 FT  B1031.2']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Count the number of each mission outcome\n",
        "outcomes_count = df['Mission_Outcome'].value_counts()\n",
        "print(outcomes_count)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "4mpHHLjmSW8d",
        "outputId": "3273331e-41b4-47d9-c264-7491f71d8fa4"
      },
      "execution_count": 28,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Mission_Outcome\n",
            "Success                             98\n",
            "Failure (in flight)                  1\n",
            "Success (payload status unclear)     1\n",
            "Success                              1\n",
            "Name: count, dtype: int64\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# Step 1: Find the maximum payload mass\n",
        "max_payload = df['PAYLOAD_MASS__KG_'].max()\n",
        "\n",
        "# Step 2: Filter boosters that carried this max payload\n",
        "boosters_with_max = df[df['PAYLOAD_MASS__KG_'] == max_payload]['Booster_Version'].unique()\n",
        "\n",
        "print(\"Booster versions with maximum payload mass:\", boosters_with_max)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "xvJu3DwlTHk1",
        "outputId": "5d9380d7-eba2-492d-f82b-6676fc878018"
      },
      "execution_count": 30,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Booster versions with maximum payload mass: ['F9 B5 B1048.4' 'F9 B5 B1049.4' 'F9 B5 B1051.3' 'F9 B5 B1056.4'\n",
            " 'F9 B5 B1048.5' 'F9 B5 B1051.4' 'F9 B5 B1049.5' 'F9 B5 B1060.2 '\n",
            " 'F9 B5 B1058.3 ' 'F9 B5 B1051.6' 'F9 B5 B1060.3' 'F9 B5 B1049.7 ']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%sql SELECT \\\n",
        "    substr(Date, 6, 2) AS Month, \\\n",
        "    Landing_Outcome, \\\n",
        "    Booster_Version, \\\n",
        "    Launch_Site \\\n",
        "FROM SPACEXTBL \\\n",
        "WHERE substr(Date, 1, 4) = '2015' \\\n",
        "  AND Landing_Outcome LIKE '%Failure (drone ship)%';"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 116
        },
        "id": "UgYAHKzwTsdl",
        "outputId": "0119b44c-9b91-4ae2-e6ae-3f40401c0cc6"
      },
      "execution_count": 32,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            " * sqlite:///my_data1.db\n",
            "Done.\n"
          ]
        },
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "[('01', 'Failure (drone ship)', 'F9 v1.1 B1012', 'CCAFS LC-40'),\n",
              " ('04', 'Failure (drone ship)', 'F9 v1.1 B1015', 'CCAFS LC-40')]"
            ],
            "text/html": [
              "<table>\n",
              "    <thead>\n",
              "        <tr>\n",
              "            <th>Month</th>\n",
              "            <th>Landing_Outcome</th>\n",
              "            <th>Booster_Version</th>\n",
              "            <th>Launch_Site</th>\n",
              "        </tr>\n",
              "    </thead>\n",
              "    <tbody>\n",
              "        <tr>\n",
              "            <td>01</td>\n",
              "            <td>Failure (drone ship)</td>\n",
              "            <td>F9 v1.1 B1012</td>\n",
              "            <td>CCAFS LC-40</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>04</td>\n",
              "            <td>Failure (drone ship)</td>\n",
              "            <td>F9 v1.1 B1015</td>\n",
              "            <td>CCAFS LC-40</td>\n",
              "        </tr>\n",
              "    </tbody>\n",
              "</table>"
            ]
          },
          "metadata": {},
          "execution_count": 32
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%sql SELECT \\\n",
        "    Landing_Outcome, \\\n",
        "    COUNT(*) AS OutcomeCount \\\n",
        "FROM SPACEXTBL \\\n",
        "WHERE Date BETWEEN '2010-06-04' AND '2017-03-20' \\\n",
        "GROUP BY Landing_Outcome \\\n",
        "ORDER BY OutcomeCount DESC;"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 239
        },
        "id": "tVH40VlOUSUN",
        "outputId": "05f24497-8c91-4bf1-dffb-248a849737ab"
      },
      "execution_count": 34,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            " * sqlite:///my_data1.db\n",
            "Done.\n"
          ]
        },
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "[('No attempt', 10),\n",
              " ('Success (drone ship)', 5),\n",
              " ('Failure (drone ship)', 5),\n",
              " ('Success (ground pad)', 3),\n",
              " ('Controlled (ocean)', 3),\n",
              " ('Uncontrolled (ocean)', 2),\n",
              " ('Failure (parachute)', 2),\n",
              " ('Precluded (drone ship)', 1)]"
            ],
            "text/html": [
              "<table>\n",
              "    <thead>\n",
              "        <tr>\n",
              "            <th>Landing_Outcome</th>\n",
              "            <th>OutcomeCount</th>\n",
              "        </tr>\n",
              "    </thead>\n",
              "    <tbody>\n",
              "        <tr>\n",
              "            <td>No attempt</td>\n",
              "            <td>10</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Success (drone ship)</td>\n",
              "            <td>5</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Failure (drone ship)</td>\n",
              "            <td>5</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Success (ground pad)</td>\n",
              "            <td>3</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Controlled (ocean)</td>\n",
              "            <td>3</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Uncontrolled (ocean)</td>\n",
              "            <td>2</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Failure (parachute)</td>\n",
              "            <td>2</td>\n",
              "        </tr>\n",
              "        <tr>\n",
              "            <td>Precluded (drone ship)</td>\n",
              "            <td>1</td>\n",
              "        </tr>\n",
              "    </tbody>\n",
              "</table>"
            ]
          },
          "metadata": {},
          "execution_count": 34
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [],
      "metadata": {
        "id": "zC6D2HnlUoiV"
      },
      "execution_count": null,
      "outputs": []
    }
  ]
}
