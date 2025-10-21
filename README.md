# We Contain Multitudes: Rachmaninoff’s Letters and Emotional Networks

This repository explores Sergei Rachmaninoff’s correspondence through a digital-humanities and musicological lens, connecting textual sentiment, emotional tone, and historical context with his creative output, focused on *Piano Concerto No. 2*. The project uses a structured CSV dataset of translated letters (1890s–1910s) to examine patterns of mood, professional exchange, and personal reflection, combining qualitative reading with computational text analysis.

## Dataset

**Source**: https://senar.ru/letters#1897 <br>
**File:** `rachmaninoff_letters.csv`  

I manually created this datasheet from this Rachmaninoff letter archive online. Each row represents one letter, containing both Russian and English text, sender/recipient metadata, and manually assigned categories for topic and emotional tone.

| Column | Description | Example |
|--------|--------------|---------|
| `letter_id` | Unique ID for each letter | 103 |
| `letter_name` | Title of the letter file | Letter to A. K. Glazunov, 1897 |
| `sender` | Author of the letter | Sergei Rachmaninoff |
| `recipient` | Recipient Russian name | А. Б. Гольденвейзеру |
| `recipient_english` | Recipient in English | A. K. Glazunov |
| `year` | Year of writing (YYYY) | 1897 |
| `date` | Date, if possible(YYYY-MM-DD) or range of year (YYYY - YYYY)  | 1897-07-31
| `location` | Location letter was written or sent from in Russian | Москва |
| `location_english` | Location (translated) | Moscow |
| `text` | Full Russian letter text | “Я очень долго Вам не писал, милый друг..." |
| `text_english` | Full English translation | “Please forgive me for disturbing you...” |
| `letter_category` | Thematic domain | professional: logistics |
| `to` | Emotional tone | neutral / ailing / melancholy / hopeful |

<br>
<br>

**View Network Analysis**: https://embed.kumu.io/d2015949b0ac3ea6cdd3083810d6dd62
<br>
**File:** `rachmaninoff_elements.csv`
| Column | Description | Example |
|--------|--------------|---------|
| `label` | The name of the node that appears in the network. For people, this is the correspondent’s name (e.g., “A. K. Glazunov”); for emotional nodes, this is the assigned mood (e.g., “melancholy”). |
| `type` | Defines the category of the node. In this dataset, nodes are classified as either Person (correspondents) or Tone (emotional categories). |
| `image` | A link to an image representing the node. For Person nodes, this is a historical portrait or Wikimedia image; for Tone nodes, it’s a color gradient chosen to visually represent the emotion. |
| `description` | A short biographical or contextual note displayed when the node is opened in Kumu. For Tone nodes, this field is blank |
<br>
<br>

**File:** `rachmaninoff_connections.csv`
| Column | Description | Example |
|--------|--------------|---------|
| `from` | In Kumu, 'from' identifies where a connection line begins. Here, it represents the sender or recipient of the letter i.e., the person who anchors the relationship. | A. V. Zatayevich |
| `to` | In Kumu, 'to' identifies where a connection line ends. In this dataset, it links the letter to its dominant mood or emotional tone. | anxious |
| `label` | The 'label' field determines what text appears on the connection line in Kumu. Here, it shows the month (in words) and year of the letter, to provide temporal context. | January 1897 |
| 'description' | The description field specifies what text appears when a node or connection is opened in Kumu. Here, it contains the full letter’s text. | "Congratulations to you, my dear friend..." |
| `type` | In Kumu, the 'type' field defines the nature of the connection between two nodes. In this dataset, every connection represents a letter, so all entries in this column are labeled "letter". This ensures Kumu recognizes all edges as part of the same network layer. | letter |

<br>

## Methods

Analytical notebooks (Python / Google Colab):

- **Text analysis:** tokenization, sentiment scoring, keyword frequency  
- **Network visualization:** mapping relationships between correspondents  
- **Emotional mapping:** e.g. plotting “valence” over time  
- **Audio connection:** comparing letter moods to harmonic/melodic tension in *Piano Concerto No. 2*

## Interpretation

This project asks: *Can computational methods reveal the emotional cadence within Rachmaninoff’s personal letters or do they only trace the shadows of what he felt?*


