name: Construire SMS Dual SIM APK

on:
  workflow_dispatch:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Télécharger le projet
        uses: actions/checkout@v4

      - name: Compiler APK Android
        uses: ArtemSBulgakov/buildozer-action@v1
        id: buildozer
        with:
          workdir: .
          buildozer_version: stable

      - name: Télécharger APK
        uses: actions/upload-artifact@v4
        with:
          name: SMS-Dual-SIM-APK
          path: ${{ steps.buildozer.outputs.filename }}