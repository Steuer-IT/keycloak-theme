# Keycloak Theme - Steuer-IT

Custom Keycloak Login-Theme für Steuer-IT.

## Lokale Entwicklung

```bash
docker compose up -d
```

Keycloak Admin-Console: http://localhost:8080/admin
Login: `admin` / `admin`

### Theme aktivieren

1. Admin-Console öffnen
2. Realm auswählen (oder neuen anlegen)
3. **Realm Settings** → **Themes** → **Login Theme** = `steuer-it`
4. Save

### Theme testen

Login-Seite aufrufen:
http://localhost:8080/realms/{realm-name}/account

Keycloak im Dev-Modus cached keine Themes. Änderungen an CSS/Templates werden nach Browser-Refresh (Strg+Shift+R) direkt sichtbar.

## Dateistruktur

```
themes/steuer-it/
└── login/
    ├── theme.properties        # Parent-Theme + CSS-Imports
    ├── resources/
    │   ├── css/styles.css      # Custom CSS
    │   └── img/                # Logo, Bilder
    └── messages/
        ├── messages_en.properties
        └── messages_de.properties
```

## Kubernetes-Deployment

Theme-Dateien als ConfigMap oder PVC mounten unter:
`/opt/keycloak/themes/steuer-it`
