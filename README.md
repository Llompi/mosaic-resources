# Community Resource Widget

An open-source, interactive resource directory for Portland, Seattle, and Spokane providing links to housing, food assistance, LGBTQ+ support, and crisis services.

## ⚠️ Important Disclaimers

### Information Accuracy
- **Resources may be outdated or incorrect** — This information was researched at a point in time and may no longer be current
- **Verify independently** — Always confirm details directly with organizations before relying on them
- **No guarantees** — We make no promises about accuracy, completeness, or availability of any listed resources
- **Not professional advice** — This is not a substitute for professional legal, medical, or crisis counseling

### Emergency Services
**🚨 FOR EMERGENCIES, CALL 911 IMMEDIATELY 🚨**

This resource directory is for informational purposes only and should never delay emergency response.

### Liability
This project is provided "AS IS" without warranty of any kind. The maintainers are not responsible for:
- Outdated or incorrect information
- Services that have changed, moved, or closed
- Any outcomes from using these resources
- Availability of this repository (may be taken down at any time)

**Seek professional guidance for all serious matters.**

## 🤝 Contributing

We **encourage and welcome** community contributions! However:

### How to Contribute
- **Report outdated information** — Open an [Issue](../../issues/new) if you find incorrect details
- **Suggest new resources** — Submit a [Pull Request](../../pulls) with additions
- **Propose new cities/states** — Open an [Issue](../../issues/new) to suggest expansion
- **Fix bugs or improve code** — PRs welcome for technical improvements

### No Guarantees
- Contributions may or may not be merged (maintainer discretion)
- No timeline commitments for reviewing PRs or Issues
- This is a volunteer project with no service level agreements

### Contribution Guidelines
1. Fork this repository
2. Make your changes in a new branch
3. Submit a Pull Request with:
   - Clear description of changes
   - Source verification for new resources (link to official website)
   - Contact information if available (phone, email, address)
4. Open Issues for:
   - Outdated resources
   - Broken links
   - Feature requests
   - City/state expansion ideas

## 🚀 Usage

### Direct Hosting
Visit the live widget at: `https://YOUR-USERNAME.github.io/REPO-NAME/`

### Embedding
Embed anywhere using an iframe:
```
<iframe 
  src="https://YOUR-USERNAME.github.io/REPO-NAME/" 
  width="100%" 
  height="800" 
  frameborder="0"
  title="Community Resources">
</iframe>
```

### Local Development
1. Clone the repository
2. Open `index.html` in a browser
3. No build process required—it's pure HTML/CSS/JS

## 📝 Customization

### Adding Resources
Edit the `resourceData` object in `index.html`:

```
{
  header: "Category Name",
  items: [
    {
      title: "Organization Name",
      description: "What they provide and who they serve",
      link: "https://official-website.org",
      linkText: "official-website.org"
    }
  ]
}
```

### Adding Cities
1. Add data to `resourceData` object
2. Add tab button in HTML
3. Add view pane in HTML
4. See full documentation in [CUSTOMIZATION.md](CUSTOMIZATION.md)

## 🎨 Features
- ✅ Fully accessible (WCAG 2.1 AA compliant)
- ✅ Keyboard navigable
- ✅ Responsive mobile design
- ✅ No dependencies or frameworks
- ✅ Privacy-focused (no tracking, no cookies)

## 📄 License

MIT License - **Free to use, modify, and distribute for any purpose, including commercial use.**

See [LICENSE](LICENSE) file for full legal text.

### What This Means
- ✅ Use it anywhere (personal, commercial, nonprofit)
- ✅ Modify it however you want
- ✅ Redistribute it freely
- ✅ No need to ask permission
- ⚠️ Must include the MIT License text in copies
- ⚠️ Provided "as is" with no warranties

## 🔗 Resources

- [Report an Issue](../../issues/new)
- [Submit a Pull Request](../../pulls)
- [View Live Demo](https://YOUR-USERNAME.github.io/REPO-NAME/)

## 💬 Support

This is a community-driven project with no formal support. For help:
1. Check existing [Issues](../../issues)
2. Open a new Issue if your question isn't answered
3. Community members may respond when available

**No guarantees on response times or resolution.**
```
**Remember:** For life-threatening emergencies, always call 911 first. For crisis support, contact organizations listed in the widget directly—don't rely solely on this directory.
```
