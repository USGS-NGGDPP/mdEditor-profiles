# mdEditor Profiles

This repository contains profiles for use with [mdEditor](https://github.com/adiwg/mdEditor). Profiles allow you to customize the metadata editing experience by specifying which components and vocabularies are available.

## Contents

- [Profiles](#profiles)
- [Manifest](#manifest)
- [Usage](#usage)
- [Contributing](#contributing)

## Profiles

The `profiles/` directory contains profile files in JSON format. Each profile defines the structure and vocabularies to be used within mdEditor.

## Manifest

The `manifest.json` file lists all available profiles in the repository. It is structured as an array of objects, each with a `url` and `name` property.

### Example Manifest File

```json
[
  {
    "url": "https://raw.githubusercontent.com/USGS-NGGDPP/mdEditor-profiles/main/profiles/nggdpp_common.json",
    "name": "NGGDPP Common"
  },
  {
    "url": "https://raw.githubusercontent.com/USGS-NGGDPP/mdEditor-profiles/main/profiles/another_profile.json",
    "name": "Another Profile"
  }
]
```

## Usage

To add a new profile to mdEditor:

1. **Add the Profile File**: Place your new profile JSON file in the `profiles/` directory.

2. **Update the Manifest**: Add an entry to the `manifest.json` file with the `url` to your new profile and an optional `name` for readability.

   - **Note**: The `name` is optional and is used only for human readability within the manifest.

3. **Load in mdEditor**: When mdEditor loads the profile, it uses the `thesauri` array within the profile to load the specified vocabularies from the URLs provided. These vocabularies will then be available in the "Keywords" tab dropdown.

**Important Terminology**:

- **Vocabulary**: A controlled list of terms used within mdEditor. In the context of profiles, vocabularies are specified in the `thesauri` array.

- **Thesauri**: In the profile JSON, the `thesauri` key contains an array of vocabulary objects, each with a `url` (required) and a `name` (optional).
