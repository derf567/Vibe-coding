# Ako nasadiť LANIZOL web na Netlify

## Metóda 1: Drag & Drop (Najjednoduchšie)

1. **Pripravte súbory:**
   - Všetky súbory sú už pripravené v tomto priečinku
   - Uistite sa, že máte všetky obrázky v `images/` priečinku

2. **Choďte na Netlify:**
   - Otvorte: https://app.netlify.com/drop
   - Nemusíte sa registrovať pre prvé nasadenie

3. **Nahrajte súbory:**
   - Označte VŠETKY súbory a priečinky v tomto projekte
   - Presuňte ich do Netlify Drop zóny
   - Alebo zbalte všetko do ZIP a nahrajte

4. **Hotovo!**
   - Netlify vám dá náhodnú URL (napr. `random-name-123.netlify.app`)
   - Stránka je okamžite živá!

---

## Metóda 2: S účtom (Odporúčané pre dlhodobé použitie)

### Krok 1: Vytvorte Netlify účet
1. Choďte na: https://app.netlify.com/signup
2. Zaregistrujte sa (zadarmo)
3. Môžete použiť GitHub, GitLab, alebo email

### Krok 2: Nasaďte stránku

**Možnosť A: Drag & Drop**
1. Prihláste sa do Netlify
2. Kliknite "Add new site" → "Deploy manually"
3. Presuňte celý priečinok projektu do drop zóny
4. Počkajte na nasadenie (1-2 minúty)

**Možnosť B: Cez GitHub (Najlepšie pre aktualizácie)**
1. Vytvorte GitHub repository
2. Nahrajte všetky súbory do repo
3. V Netlify: "Add new site" → "Import from Git"
4. Pripojte GitHub a vyberte repository
5. Netlify automaticky nasadí a bude sledovať zmeny

### Krok 3: Vlastná doména (Voliteľné)

1. V Netlify dashboarde kliknite na váš site
2. "Domain settings" → "Add custom domain"
3. Zadajte vašu doménu (napr. `lanizol.sk`)
4. Nastavte DNS záznamy u vášho registrátora domény:
   ```
   Type: A
   Name: @
   Value: 75.2.60.5
   
   Type: CNAME
   Name: www
   Value: [your-site].netlify.app
   ```
5. Netlify automaticky pridá SSL certifikát (HTTPS)

---

## Rýchly návod - Príkazový riadok (Pre pokročilých)

```bash
# 1. Nainštalujte Netlify CLI
npm install -g netlify-cli

# 2. Prihláste sa
netlify login

# 3. Nasaďte stránku
netlify deploy --prod

# Vyberte: "Create & configure a new site"
# Publish directory: . (aktuálny priečinok)
```

---

## Čo dostanete zadarmo na Netlify:

✅ Neomezená šírka pásma  
✅ Automatický SSL certifikát (HTTPS)  
✅ CDN (rýchle načítanie po celom svete)  
✅ Automatické nasadenie pri zmenách (ak používate Git)  
✅ Formuláre (až 100 odoslaní/mesiac zadarmo)  
✅ Vlastná doména  

---

## Aktualizácia stránky

### Ak používate Drag & Drop:
1. Upravte súbory lokálne
2. Choďte do Netlify dashboard
3. "Deploys" → Presuňte aktualizované súbory

### Ak používate GitHub:
1. Upravte súbory lokálne
2. Commit a push do GitHub
3. Netlify automaticky nasadí zmeny

---

## Riešenie problémov

**Obrázky sa nezobrazujú:**
- Skontrolujte, či sú všetky obrázky v `images/` priečinku
- Skontrolujte názvy súborov (case-sensitive!)

**Formulár nefunguje:**
- Netlify Forms vyžaduje špeciálny atribút
- Pridajte `netlify` alebo `data-netlify="true"` do `<form>` tagu

**404 chyba:**
- Uistite sa, že `netlify.toml` je nahraný
- Skontrolujte, či je `index.html` v root priečinku

---

## Kontakt formulár - Netlify Forms

Ak chcete, aby kontaktný formulár fungoval cez Netlify:

1. Otvorte `index.html`
2. Nájdite `<form id="contactForm">`
3. Pridajte atribút: `data-netlify="true"`
4. Príklad:
   ```html
   <form id="contactForm" data-netlify="true" name="contact">
   ```
5. Po nasadení: Netlify → Site settings → Forms
6. Tam uvidíte všetky odoslané správy

---

## Cenník Netlify

**Free tier (Zadarmo):**
- 100 GB bandwidth/mesiac
- 300 build minút/mesiac
- 100 form submissions/mesiac
- Vlastná doména
- SSL certifikát

**Pre LANIZOL web je Free tier viac než dosť!**

---

## Užitočné odkazy

- Netlify Dashboard: https://app.netlify.com
- Netlify Docs: https://docs.netlify.com
- Netlify Status: https://www.netlifystatus.com

---

**Vytvorené:** Marec 2026  
**Pre:** LANIZOL - Hydroizolácie
