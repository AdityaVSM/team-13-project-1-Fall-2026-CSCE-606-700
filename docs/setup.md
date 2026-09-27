# Setup, Running, and Testing

## Installation / Setup

### Requirements

- Ruby
- Bundler

Check the installed versions with:

```bash
ruby --version
bundle --version
```

### Install dependencies

```bash
bundle install
```

This installs the gems declared in the [Gemfile](../Gemfile): `rspec`, `rubocop`, and `sqlite3`.

## Running the Application

Start the interactive menu:

```bash
./bin/lost_and_found
```

The menu options are:

```text
1. Add a lost item
2. Add a found item
3. Find matches for a lost item
4. Mark an item as returned
5. List all lost items
6. List all found items
7. List all returned items
8. Quit
```

The CLI also accepts `--help` and `-h` to display its built-in help text.

Item name and location are required. Dates use `MM/DD/YYYY`; item IDs must be numeric. The application creates the SQLite database and schema automatically at `data/lost_and_found.sqlite3` when it connects.

## Running Tests and Generating a Coverage Report

Run the test suite with:

```bash
bundle exec rspec
```

RSpec prints a summary of examples run, failures, and pass/fail status at the end of the run — this is the coverage report currently available in this repo (there is no dedicated coverage-percentage tool such as SimpleCov configured yet).

Run the linter with:

```bash
bundle exec rubocop
```

GitHub Actions runs both commands for pull requests targeting `main`.
