# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **product specification repository** for Planda, a multi-identity location-based social network. It contains no code—only documentation, research, and planning materials.

**Purpose**: Single source of truth for product vision, feature specifications, platform research, and architectural planning.

## Repository Structure

```
planda/
├── README.md              # Repository overview and navigation
├── docs/
│   ├── product-spec.md   # Complete product specification v2.0 (~800 lines)
│   └── research/         # Platform analysis and competitive research
│       ├── README.md
│       ├── dao-governance-analysis.md      (~320 lines)
│       ├── linkedin-analysis.md            (~95 lines)
│       ├── meetup-analysis.md              (~110 lines)
│       ├── reddit-analysis.md              (~130 lines)
│       └── skool-analysis.md               (~130 lines)
```

## Product Context

**Planda** is a multi-identity social platform combining:
- **Multi-identity profiles** - Users create separate profiles for different life contexts (business, family, sports, hobbies)
- **Topic-centric communities** - Reddit-style topic-based approach where people connect around shared interests
- **Location-aware networking** - Connect online discussions with real-world local interactions
- **Community self-governance** - Each community has DAO-like governance (vote delegation, liquid democracy, trust-building)
- **Event organization** - Meetup-style features supporting communities in organizing events
- **Generalized offers system** - Jobs, events, collaborations, opportunities

### Community Governance Model

**Not a DAO, but DAO-like governance per community:**
- Simple, accessible voting and delegation system (per community)
- Vote delegation to trusted community members
- Building trust networks within communities
- Democratic decision-making without blockchain complexity
- Communities self-moderate (not platform admin-driven like Reddit)

### Community Features

Each community can provide:
- **Events** - Organize meetups and gatherings
- **Learning material** - Courses and educational content
- **Chats** - Real-time community discussions
- **Knowledge sharing** - Wiki pages and documentation
- **Requests for changes** - Liquid democracy proposals
- **Offers** - Community-specific opportunities
- **Plugin-based interactions** - Extensible community-specific features

**Key inspirations**:
- **Reddit** - Topic-based communities (but self-governed, not admin-moderated)
- **Meetup** - Event organization features
- **LinkedIn** - Professional networking
- **Skool** - Learning communities
- **DAOs** - Governance mechanisms (simplified for usability)

## Documentation Workflow

### When Making Changes to Documentation

1. **Always update related documents** - Changes to the product spec may require updates to research docs or README
2. **Maintain consistency** - Ensure terminology and concepts are consistent across all documents
3. **Update version numbers** - Product spec includes version numbers (currently v2.0)
4. **Cross-reference properly** - Use relative links between documents

### Document Relationships

- **`product-spec.md`** is the primary document—all features and requirements live here
- **`docs/research/*.md`** files inform the product spec—they analyze existing platforms to justify design decisions
- **`README.md`** provides high-level overview and navigation to all documentation

## Git Workflow

This repository follows strict PR-based development:

1. **Never push directly to main** - Always create a branch and PR
2. **Semantic commits** - Follow conventional commit format:
   - `docs:` for documentation updates
   - `refactor(docs):` for documentation reorganization
   - Examples: `docs: Update product spec with new governance features`
3. **One PR per logical change** - Keep PRs focused and reviewable
4. **Descriptive PR bodies** - Include Summary, Changes, and Test Plan sections

### Creating PRs

```bash
# Create feature branch
git checkout -b docs/feature-name

# Make changes and commit with semantic message
git add .
git commit -m "docs: Brief description

- Detailed change 1
- Detailed change 2"

# Push and create PR
git push -u origin docs/feature-name
gh pr create --title "docs: Brief description" --body "..."
```

## Common Tasks

### Adding New Research

1. Add markdown file to `docs/research/`
2. Update `docs/research/README.md` to list the new document
3. Reference insights in `docs/product-spec.md` where relevant
4. Update main `README.md` if it affects the documentation structure

### Updating Product Specification

1. Read relevant research documents first to understand context
2. Edit `docs/product-spec.md` with new features or changes
3. Update version number if making major changes
4. Ensure consistency with existing features and terminology
5. Cross-reference research that informed the changes

### Reorganizing Documentation

When moving or restructuring documents:
1. Use `git mv` to preserve history
2. Update all internal links in affected documents
3. Update `README.md` to reflect new structure
4. Update `docs/research/README.md` if research files are affected

## Part of TopLocs Ecosystem

This repository is part of the larger TopLocs ecosystem of decentralized community platforms. Implementation repositories will be created as development progresses based on specifications in this repository.

## Key Considerations

- **No build/test commands** - This is a documentation-only repository
- **Focus on clarity** - Documentation should be accessible to both technical and non-technical stakeholders
- **Evidence-based design** - Product decisions should reference research analysis
- **Version control** - Track major product specification changes with version numbers
