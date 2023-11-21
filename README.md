Pierwsza część odnosi się do obliczania kątów torsyjnych: linijki 5-39.
Druga część odnosi się do do generowania wykresu Ramachandrana dla określonej struktury białka na podstawie pliku PDB : linijki 38 - 65

Część 1
Poniższy kod jest skryptem języka Python używającym biblioteki Biopython do analizy struktur RNA zapisanych w formacie PDB (Protein Data Bank). Jest on zaprojektowany do obliczania kątów torsyjnych, które są kluczowe dla zrozumienia trójwymiarowej struktury RNA. Oto szczegółowy opis poszczególnych części skryptu:

  Importowanie bibliotek i modułów:
        biopython to biblioteka używana do analizy danych biologicznych.
        google.colab umożliwia upload plików w środowisku Google Colab.
        Bio.PDB to moduł Biopython służący do parsowania plików PDB.
        numpy to biblioteka do obliczeń naukowych w Pythonie.
        Bio.PDB.vectors umożliwia obliczenia wektorowe, takie jak obliczanie kątów torsyjnych.

  Wczytywanie plików:
        Użytkownik przesyła plik PDB o nazwie "1EHZ.PDB" za pomocą interfejsu Google Colab.

  Definicja słownika torsion_atoms:
        Słownik zawiera nazwy atomów używanych do obliczania siedmiu głównych kątów torsyjnych w RNA: alpha, beta, gamma, delta, epsilon, zeta, chi.
        Dla kąta chi, który zależy od typu bazy (puryny lub pirymidyny), definiuje dwa zestawy atomów: chi_pyrimidines i chi_purines.

  Funkcja get_torsion_angle:
        Oblicza kąt torsyjny między czterema atomami, korzystając z funkcji calc_dihedral.

  Funkcja get_chi_atoms:
        Wybiera odpowiedni zestaw atomów dla kąta chi, w zależności od tego, czy badana reszta jest puryną czy pirymidyną.

  Funkcja calculate_rna_torsion_angles:
        Parsuje strukturę RNA z pliku PDB.
        Iteruje przez modele, łańcuchy i reszty, obliczając kąty torsyjne dla każdej reszty.
        Dla kąta chi dokonuje specjalnego wyboru atomów w zależności od typu bazy.
        Wyniki są zapisywane do pliku CSV.

  Wywołanie funkcji:
        Skrypt wykonuje analizę na konkretnym pliku PDB (tutaj przykładowo 1EHZ.pdb) i zapisuje wyniki do pliku.

Powyższy kod stanowi przykład zastosowania obliczeń bioinformatycznych do analizy strukturalnej RNA, umożliwiając głębsze zrozumienie ich konformacji i potencjalnych interakcji.

Część druga
kod jest skryptem Python wykorzystującym Biopython i Matplotlib do generowania wykresu Ramachandrana dla określonej struktury białka na podstawie pliku PDB (Protein Data Bank). Wykres Ramachandrana jest narzędziem służącym do analizy konformacji białek poprzez wizualizację kątów torsyjnych ϕ (phi) i ψ (psi) w ramach łańcuchów polipeptydowych. Oto szczegółowy opis poszczególnych części kodu:

   Importowanie bibliotek:
        biopython służy do analizy danych biologicznych, w tym plików PDB.
        matplotlib.pyplot i numpy są używane do tworzenia i manipulowania wykresami oraz do obliczeń matematycznych.
        files z modułu google.colab umożliwia wczytanie plików w środowisku Google Colab.

   Wczytywanie pliku PDB:
        Użytkownik może przesłać plik PDB za pomocą interfejsu Google Colab.
        Nazwa pliku PDB jest zapisywana do zmiennej pdb_filename.

  Definicja funkcji plot_ramachandran:
        Funkcja parsuje strukturę białka z pliku PDB.
        Korzystając z klasy PPBuilder, konstruuje peptydy i oblicza kąty φ i ψ dla każdego aminokwasu.
        Kąty są przekształcane na stopnie i dodawane do listy phi_psi_list.
        Kąty są klasyfikowane na podstawie ich lokalizacji w konkretnych regionach wykresu Ramachandrana (α-helisa, β-sheet, inne).
        Kolory punktów na wykresie są zależne od tej klasyfikacji.

   Tworzenie i wyświetlanie wykresu Ramachandrana:
        Wykres jest tworzony jako scatter plot (wykres punktowy).
        Tytuł, etykiety osi, zakresy osi i kolory punktów są określone.
        Wykres jest wyświetlany, pokazując dystrybucję kątów φ i ψ.

  Wywołanie funkcji:
        Funkcja plot_ramachandran jest wywoływana z identyfikatorem struktury (w tym przypadku "1MBO") i nazwą wczytanego pliku PDB.

Kod ten jest użytecznym narzędziem do wizualnej analizy konformacji białek, dając wgląd w ich strukturę drugorzędową i stabilność. Wykres Ramachandrana jest klasycznym narzędziem w bioinformatyce i biologii strukturalnej.
