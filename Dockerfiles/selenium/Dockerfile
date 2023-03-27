# Użyj obrazu selenium/standalone-chrome jako podstawy
FROM selenium/standalone-chrome:latest

# Ustaw katalog roboczy
WORKDIR /app

# Zaktualizuj system i zainstaluj wymagane pakiety
USER root
RUN apt-get update && apt-get install -y \
    openjdk-11-jdk \
    maven

# Skopiuj plik pom.xml i katalog z kodem źródłowym
COPY pom.xml .
COPY src ./src

# Przełącz się na użytkownika selenium
USER seluser

# Otwórz port 4444 dla Selenium Grid
EXPOSE 4444

# Ustaw komendę, która będzie uruchamiana w kontenerze
CMD ["mvn", "clean", "test"]
