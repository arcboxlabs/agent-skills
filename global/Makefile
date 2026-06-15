PARTS := $(wildcard parts/*.md)
COMMON := $(filter-out %.claude.md %.codex.md,$(PARTS))
CLAUDE_PARTS := $(sort $(COMMON) $(wildcard parts/*.claude.md))
CODEX_PARTS  := $(sort $(COMMON) $(wildcard parts/*.codex.md))

all: CLAUDE.md CODEX.md

CLAUDE.md: $(CLAUDE_PARTS)
	awk 'FNR==1 && NR!=1 {print ""} 1' $^ > $@

CODEX.md: $(CODEX_PARTS)
	awk 'FNR==1 && NR!=1 {print ""} 1' $^ > $@

clean:
	rm -f CLAUDE.md CODEX.md

.PHONY: all clean
