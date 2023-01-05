# Cold Emails.

!!! warning "These tactics are only used in a setting to gain new agency clients."


![Bits Please Logo](../images/logo.png)

## Cold Prospects

### Introductie

<!-- Shortly introduce yourself and the company -->

> Shortly introduce yourself and the company.

```bash
Hey is dit Shaniel van <company-name>? 
Met Andy van Bits Please Technologies.
We zijn een consulting en detacheringsbedrijf gespecialiseerd in het helpen van bedrijven zoals het uwe om technologie in te zetten voor groei.
```

> Politely make sure you're not calling at the wrong time.

```
Bel ik u gelegen?
```

> Vraag over het bedrijf.

```bash
Ik zou graag meer willen weten over uw bedrijf en de specifieke softwareontwikkelings- en onderhoudsbehoeften die u heeft. Kunt u mij wat meer vertellen over uw huidige uitdagingen en doelen op dit gebied?
```


Then move the `app,pages` folders into the `src` folder.

> the `-t, --target-directory=DIRECTORY` flag for the `mv` command moves all SOURCE arguments into DIRECTORY

```bash
mv -t src app pages
```

After you've moved these folders to the `src` folder root of your project. Navigate into the directory and create these folders and add placeholder files. `eg. hooks/hooks.placeholder`

```
src/
├─ config/
├─ hooks/
├─ interfaces/
├─ services/
├─ utils/
```

> We will remove the placeholder files when we start using the directories.

```bash
# naviagete to `src` directory
cd src

# make tconfig hooks interfaces services utils directories
mkdir components config hooks interfaces services utils

# add placeholder files to directories
touch components/components.placeholder config/config.placeholder hooks/hooks.placeholder interfaces/interfaces.placeholder services/services.placeholder utils/utils.placeholder
```