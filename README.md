# Authentik Frosted Theme

A frosted-glass custom CSS theme for [authentik](https://goauthentik.io/).

## Installation

1. Download [`theme.css`](./theme.css) and copy its entire contents.
2. In the authentik Admin interface, go to **System → Brands**.
3. Edit **authentik Default** or the Brand assigned to your domain.
4. Under **Branding settings**, replace the contents of **Custom CSS** with the downloaded stylesheet, then save the Brand.
5. Refresh the page. If an older version is still visible, perform a hard refresh or clear the browser cache.

> [!NOTE]
> The theme was tested with authentik 2026.5.6. If you find a visual bug with another version or flow configuration, please [open an issue](https://github.com/iUnstable0/authentik-frosted-theme/issues).

## Optional customization

### Use the demo background

To use the Earth image shown in the screenshots:

1. Download [`flow.jpg`](./flow.jpg).
2. In the Admin interface, go to **Customization → Files** and upload it.
3. Edit your Brand and select the uploaded image as its default flow background.

### Match the interface shown in the screenshots

The following Brand attributes reproduce the dark background, three-column layout, and navigation options used for the screenshots. They are optional and are not required for the login theme.

Add them under **System → Brands → your Brand → Attributes**:

```yaml
settings:
  theme:
    base: dark
    background: >
      background:
        radial-gradient(circle at 15% 10%, rgba(62, 132, 180, 0.16), transparent 35%),
        radial-gradient(circle at 85% 85%, rgba(72, 79, 112, 0.12), transparent 35%),
        linear-gradient(135deg, #05070b 0%, #0a1018 55%, #080b10 100%);
      background-attachment: fixed;
  layout:
    type: 3-column
  navbar:
    userDisplay: name
  enabledFeatures:
    search: true
    settings: true
    apiDrawer: false
    applicationEdit: false
    notificationDrawer: false
```

### Add text beside the Brand logo

The theme does not add a label by default. To display a domain or company name beside the logo, find this line in [`theme.css`](./theme.css):

```css
--iu-brand-label: none;
```

Replace `none` with a quoted label:

```css
--iu-brand-label: "example.com";
```

## Preview

<img width="2966" height="1824" alt="Frosted authentik login screen" src="https://github.com/user-attachments/assets/a960040f-3d8c-4e75-b4c4-de0848ab8721" />

<img width="2966" height="1824" alt="Frosted authentik user interface" src="https://github.com/user-attachments/assets/292d8c0f-6955-4ba7-8301-f7900ddcb8ac" />

<img width="1483" height="912" alt="Frosted authentik dashboard" src="https://github.com/user-attachments/assets/020dc1e7-91fd-4cab-99ba-af4f89c6b988" />

<img width="1483" height="912" alt="Frosted authentik applications view" src="https://github.com/user-attachments/assets/d2b07c31-5b5f-4f65-81b6-b94f580c7307" />

<img width="1483" height="912" alt="Frosted authentik settings view" src="https://github.com/user-attachments/assets/2ea19eb6-4132-4684-bad2-a42ae1240dba" />
