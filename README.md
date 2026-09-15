# Weapon Collection Manager

A WPF (C#/.NET) desktop app for browsing, editing, and persisting a collection of weapon data. Built for the VGP232 Tools and Pipelines class.

## Features

- **Load / Save** weapon data in three formats: CSV, JSON, and XML (format is chosen automatically from the file extension).
- **Add / Edit / Remove** weapons through a dedicated edit dialog.
- **Filter** the list by weapon type and by name (substring match).
- **Sort** by column: Name, Type, Rarity, BaseAttack, Passive, or SecondaryStat.

## Weapon Data

Each weapon has the following fields:

| Field | Type |
|---|---|
| Name | string |
| Type | enum (Sword, Polearm, Claymore, Catalyst, Bow, None) |
| Image | string |
| Rarity | int |
| BaseAttack | int |
| SecondaryStat | string |
| Passive | string |

CSV files use the column order above, with a header row.

## Project Structure

- `MainWindow.xaml(.cs)` — main UI: list view, filters, sort controls, load/save/add/edit/remove actions.
- `EditWeaponWindow.xaml(.cs)` — dialog for adding or editing a single weapon.
- `Weapon.cs` — weapon data model, CSV parsing, and sort comparers.
- `WeaponCollection.cs` — `List<Weapon>` with load/save logic for CSV, JSON, and XML, plus query helpers (highest/lowest base attack, filter by type/rarity).
- `IPersistence.cs` — persistence interface implemented by `WeaponCollection`.
- `UnitTests.cs` — unit tests.
- `data.csv`, `data2.csv`, `output.csv` — sample weapon data files.

## Running

Open `VGP 232 – Assignment 1.sln` in Visual Studio and run. Requires .NET / WPF support (Windows).
