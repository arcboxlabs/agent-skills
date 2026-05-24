PARTS := $(wildcard parts/*.md)
COMMON := $(filter-out %.claude.md %.codex.md,$(PARTS))
CLAUDE_PARTS := $(sort $(COMMON) $(wildcard parts/*.claude.md))
CODEX_PARTS  := $(sort $(COMMON) $(wildcard parts/*.codex.md))

all: CLAUDE.md CODEX.md

CLAUDE.md: $(CLAUDE_PARTS)
	cat $^ > $@

CODEX.md: $(CODEX_PARTS)
	cat $^ > $@

clean:
	rm -f CLAUDE.md CODEX.md

.PHONY: all clean
