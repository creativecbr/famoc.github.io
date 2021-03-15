# **FAMOC**


## Backup kontaktów (grup kontaktów) 
    DA, DA + KNOX (kontakty tylko w PP),
    DO, COPE i BYOD (kontakty tylko w WP)

> ### Policy/Advanced/Backup setting
> - Ustawić Business Contact sync interval na **Once a day**.
> - Wybrać opcje np. *Contacts from user group* i wybrać dwie grupy różnych kontaktów.
> - Zrobić enrollment i sprawdzić czy kontakty biznesowe weszły.
> - W polityce dodaj/usuń kontakt do grupy, usuń drugą grupę.
> - Dodaj prywatne kontakty na PP.
> - Usuń jakiś kontakt na WP oraz zmień dane innego.
> - Dodaj konto google z kontaktami na PP.
> - Zsynchronizuj z nowego UI kontakty na urządzeniu (WP).
> - Sprawdź czy: 
>   - kontakty biznesowe są aktualne z polityką?
>   - kontakty PP nie zostały naruszone?
>   - kontakty z konta google są nadal dostępne?

___

<br />

## APK

> ### Instalacja pliku .apk z FAMOC
> - Zainstaluj .apk na urządzeniu z poziomu FAMOC w zależności od trybu w PP lub WP.
> - Sprawdź czy: 
>   - aplikacja się zainstalowała?
>   - aplikację można uruchomić? 
>   - została dodana w Famocu w zainstalowanych?
> - Uruchom dodatkowo aplikację z Famoca.
> - Odinstaluj aplikację z Famoca.
> - Sprawdź czy: 
>   - aplikacja odinstalowała sie poprawnie?
>   - czy Famoc nie zrzucił błędu w logach?
>   - czy w Famocu aplikacja jest przeniesiona do odinstalowanych?

___

<br />

## MGP (instalation & configuration)

> ### Instalacja aplikacji z zarządzalnego sklepu Google Play
> - Zainstaluj aplikację z Google Play udostępnioną w MGP z poziomu Famoc (advanced/UI) w zależności od trybu w PP lub WP lub w obu jednocześnie.
> - Zainstaluj aplikację z Google Play udostępnioną w MGP z poziomu zarzązdanego sklepu na urządzeniu.
> - Zainstaluj aplikację MGP z wprowadzoną konfiguracją np. Strongswan.
> - Sprawdź czy:
>   - operacja instalacji wykonała się poprawnie?
>   - czy aplikacja zainstalowała się na urządzeniu i czy można ja uruchomić z poziomu urządzenia?
>   - czy aplikacja została dodana w Famocu w zainstalowanych aplikacjach (advanced/UI) apk w części PP i WP?
>   - czy na zainstalowanej na urządzeniu aplikacji MGP działa zapisana konfiguracja?

___

<br />

## VPP

> ### TODO

___

<br />

## AppStore

> ### TODO


___

<br />

## IPA

> ### TODO


___

<br />

## Data wipe on SIM card change

> ### Wipe reset po zmianie karty SIM
> - Włoż kartę sim do urządzenia.
> - Ustaw w polityce *Security options/Wipe policy* opcję **Data wipe on SIM card change**.
> - Odśwież politykę na telefonie.
> - Wyciągnij kartę SIM.
> - Urządzenie po chwili powinno automatycznie się wyczyścić do ustawień fabrycznych za wyjatkiem urządzeń dodanych w BYOD, gdzie powinien zostać usunięty tylko kontener WP.

___

<br />

## FRP (factory reset protection)
    (DO, COPE, COSU)

> ### Blokowanie urządzenia po wipe resecie kontem Google 
> - Ustaw w polityce w *Security options/Wipe policy/Factory reset protection (FRP)* opcję **Unlock the device with an active account** lub **Unlock the device with an acciunt from the list** i dodaj *Google user ID* np. 
> > 105641089322754872938 - ID konta famoctester@gmail.com.
> - W przypadku ustawienia opcji **Unlock the device with an active account** dodaj konto Google w części personalnej urządzenia.
> - Wyślij z Famoca na urządzenie operację **Wipe device**.
> - Po przywróceniu ustawień fabrycznych w trakcie procesu startowego urządzenia powinno być wymagane zalogowanie do konta Google z listy w *Wipe policy* lub aktywnego konta googlowego użytkownika przed wipem urządzenia.


___

<br />

## OTA update policy - postponed

> ### Ukrywanie/blokada aktualizacji systemowych telefonu
> - Upewnij się, że urządzenie ma dostępną aktualizację.
> - Ustaw w polityce *Security options/Update policy* opcję **OTA update policy** na **Postponed**.
> - W przypadku Samsunga zalecane jest zablokowanie wszystkich opcji w OTA menu.
> - Odśwież politykę na urządzeniu.
> - Sprawdź czy aktualizacje zostały wyszarzone/zablokowane.

___

<br />

## [sec] Unknown sources lock / [wp] Enable unknown sources

> ### Blokowanie instalacji aplikacji z nieznanych źródeł 
> - Pobierz i zainstaluj aplikację z nieznanego źródła np. **https://www.f-droid.org/** w odpowiednich kontenerach np. bezpośrednio przez przeglądarkę.
> - Sprawdź czy instalacja przebiegła pomyślnie.
> - Ustaw w polityce *Security options/Installer policy* opcję **Unknown sources lock**.
> - (Dla odpowiednich trybów) Ustaw w polityce WP w *Work profile/Work profile restrictions* opcję **Enable unknown sources**.
> - Spróbuj ponownie zainstalować inne aplikacje z nieznanych źródeł w odpowiednich kontenerach, z powyższym ustawieniem powinno udać się zainstalować aplikację tylko w kontenerze WP, PP powinno odrzucić możliwosć instalacji.
> - Odznacz opcję **Unknown sources lock** w *Security options/Installer policy* (oraz w odpowiednich trybach odznacz **Enable unknown sources** w *Work profile/Work profile restrictions).
> - Spróbuj ponownie zainstalować inne aplikacje z nieznanych źródeł w odpowiednich kontenerach, z powyższym ustawieniem powinno nie udać się zainstalować aplikacji w kontenerze WP, natomiast w PP powinno to normalnie działać.


___

<br />

## Car mode

> ### Symulowanie ruchu pojazdu z nałożonymi restrykcjami
> - Jeśli posiadasz aplikację Lockito oraz masz skonfigurowaną ją jako wskaźnik lokalizacji możesz **pominąć ten krok**.
>   - Zainstaluj na urządzeniu aplikację Lockito dostępną [tutaj](https://m.apkpure.com/pl/lockito-%E2%80%93gps-itinerary-faker-spoofer/fr.dvilleneuve.lockito/download?from=details).
>    - Ustaw w ustawieniach deweloperskich aplikację *Lockito* jako pozorującą lokalizacje.
> - Wejdź w *Security options/Restriction rules* oraz kliknij przycisk **Add rule**.
> - Uzupełnij pole *Name* oraz kliknij **Add condition**, po czym wybierz *Condition type* jako **Speed** oraz ustaw *Value* na np. **50** km/h i kliknij **Add**.
> - Udaj się do restrykcji w polityce, którą chciałbyś nałożyć, warto przetestować wszystkie, ale tutaj posłużymy się przykładem **Bluetooth lock** z *Security options/Network policy*. Pamiętaj aby zaznaczyć checkboxa w **drugiej** kolumnie, która nazywa się *Restriction mode (time/geo/speed)*.
> - Zapisz i odśwież politykę na urządzeniu.
> - W aplikacji *Lockito* wyznacz drogę i symuluj warunki, które będą łamać restrykcję oraz je spełniać.
> - Sprawdź czy Twoja restrykcja po złamaniu działa, np. *bluetooth* zostanie wyłączony bez możliwości włączenia, dopóki nie zostanie zmniejszona prędkość. (Opóźnienie po przekroczeniu zasad może sięgać kilkunastu sekund)


___

<br />

## Disable manual unenrollment [?]

> ### Wyłączanie możliwości ręcznego unenrollemntu
> - Upewnij się, że w ??aplikacji famoc??, możesz ręcznie usunąć enrollment.
> - Ustaw opcję **Disable manual unenrollment** w *Security options/Hardware policy*. 
> - Zapisz i odśwież politykę.
> - Sprawdź czy nadal możesz ręcznie usunąć enrollment.


___

<br />

## Development mode lock

> ### Zablokowanie ustawień programistycznych
> - Upewnij się, że możesz uruchomić opcje programistyczne klikając kilka razy na *Numer wersji* w ustawieniach urządzenia.
> - Ustaw w polityce *Security options/Hardware policy* opcje **Development mode lock**.
> - Odśwież politykę.
> - Sprawdź czy nadal możesz uruchomic opcje programistyczne.


___

<br />

## Factory reset lock (wipe policy)

> ### Zablokowanie możliwości przywracania urządzenia do ustawień fabrycznych
> - Upewnij się, że możesz rozpocząć resetowanie urządzenia do ustawień fabrycznych.
> - Ustaw w polityce *Security options/Wipe policy* opcje **Factory reset lock**.
> - Odśwież politykę.
> - Sprawdź czy nadal możesz przywrócic urządzenie do ustawień fabrycznych.


___

<br />

## Prevent users from configuring credentials in the managed keystore [?]

> ### Zablokowanie użytkownikowi możliwości modifikowania certyfikatów w WP
> - Upewnij się, że możesz konfigurować certyfikaty w ustawieniach (dodawać, usuwać) na WP oraz z Famoca.
> - Ustaw w polityce *Hardware policy/Work profile restrictions* opcję **Prevent users from configuring credentials in the managed keystore**.
> - Odśwież politykę.
> - Zainstaluj/odinstaluj certyfikat w WP z Famoca.
> - Sprawdź czy instalacja przebiegła pomyślnie i czy certyfikat został dodany w Famocu.
> - Spróbuj zmodyfikować certyfikaty w WP z urządzenia, powinno być to niedozwolone.


___

<br />

## Application installer lock 

> ### Zablokowanie możliwości instalacji aplikacji 
> - Upewnij się, że możesz instalować aplikacje ze sklepu *Google Play* lub z plików .apk, w odpowiedni sposób, dopasowany do trybu urządzenia.
> - Ustaw w polityce *Security options/Installer policy* opcje **Application installer lock**.
> - Odśwież politykę.
> - Sprawdź czy nadal możesz instalować aplikacje.


___

<br />

## Disable accounts modification

> ### Zablokowanie możliwości zmiany kont na urządzeniu
> - Upewnij się, że możesz dodać nowe konto na urządzeniu w ustawieniach, np. konto *Google*, w zależności od trybu, dla WP i PP.
> - Ustaw opcje **Disable accounts modification** w polityce, znajdziesz ją w zależności od trybu, dla PP: *Security options/Application restrictions*, oraz dla WP: *Work profile/Work profile restrictions*.
> - Odśwież politykę.
> - Sprawdź czy nadal możesz modifikować konta w ustawieniach.


___

<br />

## Phone settings lock

> ### Zablokowanie możliwości wejścia w ustawienia
> - Upewnij się, że możesz wejść w ustawienia urządzenia.
> - Ustaw w polityce *Security options/Application restrictions* opcje **Phone settings lock**.
> - Odśwież politykę.
> - Sprawdź czy nadal możesz wejść w ustawienia, najlepiej różnymi ścieżkami.


___

<br />

## Application blacklist / Device Owner application policy [?]

> ### Blokowanie listy aplikacji
> - Zależnie od trybu, zainstaluj aplikacje na WP i/lub PP.
> - W polityce *Security options/Application policy/Device Owner application policy* ustaw **Block application from the list** i na liście umieść aplikacje, które zostały zainstalowane. 
> - Odśwież politykę.
> - Sprawdź, czy możesz uruchomić aplikacje umieszczone na blackliście. 


___

<br />

## Kiosk mode -> Czy sie zaklada (Android/iOS)

> ### TODO (in docs)


___

<br />

## Kiosk mode -> Czy dalej aktywny po aktualizacji agenta

> ### TODO (in docs)


___

<br />

## COSU -> Kiosk na launchera w DO
    
> ### TODO (in docs)



___

<br />

## Change of lock code

> ### Zmiana kodu blokady urządzenia z poziomu Famoca
> - Upewnij się, że na urządzeniu założony jest kod blokady.
> - Wejdź w new UI, wybierz swoje urządzenie i przy pomocy action boxa(trzy kropki) wyszukaj opcję **Reset lock code** oraz wpisz w pole *Temporary lock code* swój wybrany kod np. ***1304*** po czym wyślij akcję.
> - Sprawdź, czy kod blokady został zmieniony na urządzeniu.


___

<br />

## Setting for device lock code

> ### Skonfigurowanie wymagań kodu blokady urządzenia
> - Sprawdź, jakie wymagania aktualnie zostały ustawione do haseł blokady.
> - Utwórz albo znajdź odpowiednią konfigurację lock code w *Config center*, gdzie typem konfiguracji jest *Settings for device lock code*, przykładową konfiguracją na dtg jest np. **NB Settings for lock code (Pass/Pin/Pattern, 4)**.
> - Wyślij konfigurację na urządzenie w zależności od trybu (WP lub PP).
> - Sprawdź czy wymagania kodu blokady się zmieniły. 


___

<br />

## Strongswan VPN (Strongswan VPN configuration cert)

> ### Instalacja Strongswana w celu połączenia VPN z certyfikatem
> - Upewnij się, że na urządzeniu zainstalowana jest aplikacja Strongswan 1.7.0.6 (build Famoc), jeśli nie, dostępna jest [tutaj](file://nas1/02.%20Development/strongSwan/).
> - Następnie należy poszukać/utworzyć odpowiednią konfigurację (musi ona zawierać certyfikat strongswanCert, odpowiednie credentiale)
> - Wyślij konfigurację na ten kontener, w którym został zainstalowany strongswan.
> - Połącz się z VPN w aplikacji na danych odebranych z konfiguracji.
> - Połącz się na adres ***https://detrick.l.fancyfon.com*** z pomocą internetu zewnętrznego(np. dane mobilne), jeśli wszystko jest w porządku, VPN z konfiguracją działa poprawnie.


___

<br />

## VPN Cisco Any Connect

> ## TODO
