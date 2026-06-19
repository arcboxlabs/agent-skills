PARTS := $(wildcard parts/*.md)
COMMON := $(filter-out %.claude.md %.codex.md %.amp.md,$(PARTS))
CLAUDE_PARTS := $(sort $(COMMON) $(wildcard parts/*.claude.md))
CODEX_PARTS  := $(sort $(COMMON) $(wildcard parts/*.codex.md))
AGENTS_PARTS := $(sort $(COMMON) $(wildcard parts/*.amp.md))

all: CLAUDE.md CODEX.md AGENTS.md

CLAUDE.md: $(CLAUDE_PARTS)
	awk 'FNR==1 && NR!=1 {print ""} 1' $^ > $@

CODEX.md: $(CODEX_PARTS)
	awk 'FNR==1 && NR!=1 {print ""} 1' $^ > $@

AGENTS.md: $(AGENTS_PARTS)
	awk 'FNR==1 && NR!=1 {print ""} 1' $^ > $@

clean:
	rm -f CLAUDE.md CODEX.md AGENTS.md

.PHONY: all clean
