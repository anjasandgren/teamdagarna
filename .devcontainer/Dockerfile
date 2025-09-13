# 🟢 Starta från en modern Node-bild
FROM node:20

# 🛠 Installera verktyg (valfritt, men bra att ha)
RUN apt-get update && apt-get install -y git curl nano && rm -rf /var/lib/apt/lists/*

# 📂 Skapa en arbetsmapp i containern
WORKDIR /usr/src/app

# 📦 Kopiera package.json och package-lock.json först (för caching)
COPY package*.json ./

# 🔧 Installera globala verktyg
RUN npm install -g @angular/cli firebase-tools

# 📥 Installera projektets beroenden
RUN npm install

# 📂 Kopiera resten av projektet
COPY . .

# 🚪 Öppna porten Angular använder (4200)
EXPOSE 4200

# 🚪 Öppna porten Firebase emulator/deploy (5000+)
EXPOSE 5000

# ▶️ Standardkommando
CMD ["bash"]
