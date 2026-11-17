# Results: 411 Linux perf PMU Analysis Harness

**Main goal:** Analyze CPU IPC, branch, cache, and stall behavior under load  
**Tools:** Run perf stat -x, -e <events> -- <stress-ng command> for each yaml workload command

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_145 · recorded 2026-11-17). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 26.04.1 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-17T11:00:18Z · status **N/A-EXPECTED** (exit 0)
- **Time (mm:ss):** setup 00:33 · benchmark 00:05 · whole run 00:43
- **Source:** run 411_20261117_110018
- **Command:** `bash run_benchmark.sh --smoke --num-cpus 1 --workload-commands "stress-ng --cpu {num_cpus} --timeout {duration}s --metrics-brief,stress-ng --cache {num_cpus} --timeout {duration}s --metrics-brief" --event-list cycles,cpu-cycles,instructions,branches,branch-misses,cache-references,cache-misses,L1-dcache-loads,L1-dcache-load-misses,LLC-loads,LLC-load-misses,dTLB-load-misses,iTLB-load-misses,stalled-cycles-frontend,stalled-cycles-backend,context-switches --duration 2`

| # | Metric | Result |
|---|---|---|
| 1 | Instructions per cycle, all commands combined (instructions_per_cycle_ipc) | na (expected: perf not installed for kernel 6.8.0-138-generic) |
| 2 | Branch misprediction rate, all commands combined, pct (branch_misprediction_rate) | na (expected: perf not installed for kernel 6.8.0-138-generic) |
| 3 | Cache misses per 1,000 instructions, all commands combined (cache_misses_per_1000_instructions) | na (expected: perf not installed for kernel 6.8.0-138-generic) |
| 4 | Pipeline stalls, all commands combined, pct (pipeline_stall_pct) | na (expected: perf not installed for kernel 6.8.0-138-generic) |
| 5 | Context switches per second, all commands combined (context_switches_during_workload_switches_s) | 24.45291139080009 |
<!-- /profile:smoke -->
