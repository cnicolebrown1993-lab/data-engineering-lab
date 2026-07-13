from pathlib import Path

import pandas as pd

# path to the root of the repository
PROJECT_ROOT = Path(__file__).resolve().parents[1]

CSV_FOLDER = PROJECT_ROOT / "CSV files"

TOP_ANIME_FILE = CSV_FOLDER / "top_1000_animes.csv"
WATCHED_ANIME_FILE = CSV_FOLDER / "most_watched_anime_dataset_100_entries.csv"
MANGA_FILE = CSV_FOLDER / "best-selling-manga.csv"


def load_datasets() -> tuple[pd.DataFrame, pd.DataFrame, pd.DataFrame]:
    """load the three raw csv datasets."""

    top_anime = pd.read_csv(TOP_ANIME_FILE)
    watched_anime = pd.read_csv(WATCHED_ANIME_FILE)
    manga = pd.read_csv(MANGA_FILE)


    return top_anime, watched_anime, manga

def print_profile(name:str, dataframe:pd.DataFrame) -> None:
    """Print basic profiling information for one dataset."""
        
    print(f"\n{name}")
    print("-" * len(name))
    print(f"Rows: {len(dataframe):,}")
    print(f"columns: {len(dataframe.columns)}")
    print(f"duplicate rows: {dataframe.duplicated().sum()}")

    print("\nMissing values:")
    print(dataframe.isna().sum())

def main() -> None:
    top_anime, watched_anime, manga = load_datasets()

    print_profile("Top 1000 Anime", top_anime)
    print_profile("Most Watched Anime", watched_anime)
    print_profile("Best-Selling Manga", manga)

if __name__ =="__main__":
    main()

