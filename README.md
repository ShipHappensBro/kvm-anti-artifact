# Kvm Anti Artifact

Experimental Linux kernel development focused on KVM virtualization, low-level system behavior, and performance optimization.

The project explores kernel-level modifications, virtualization internals, and alternative execution paths to investigate their impact on latency, performance, and system behavior.

## Project Goals

- **KVM Optimization** — investigate VM-exit overhead, guest execution paths, and virtualization latency.
- **Low-Level Development** — experiment with x86 architecture, CPU instructions, VMCS, and processor state management.
- **Kernel Internals** — study and modify Linux kernel subsystems to explore alternative implementation approaches.
- **Performance Analysis** — measure and compare the effects of kernel modifications under different workloads.
- **Extensibility** — maintain a modular, evolving codebase for future experiments, optimizations, and architectural changes.

## Current Focus

The initial development focuses on Intel VMX and KVM, including:

- CPUID interception and cached result handling.
- RDTSC / RDTSCP emulation and virtual TSC scaling.
- Alternative VM-exit handling paths.
- Investigation of instruction execution overhead in virtualized environments.

These are initial experiments, not the final scope of the project.

## Development Approach

The project follows an iterative experimental workflow:

1. Identify a kernel or virtualization behavior to investigate.
2. Implement a targeted modification.
3. Build a custom Linux kernel.
4. Test the modification under controlled conditions.
5. Measure performance and validate correctness.
6. Refine the implementation or explore new approaches.

Correctness, reproducibility, and measurable results are important parts of the development process.

## Building and Installing

The project is developed against a specific Linux kernel source tree. Each modification may depend on the kernel version and configuration.

Typical workflow:

```bash
# Apply a patch to the kernel source tree
git apply --check patches/<patch-name>.patch
git apply patches/<patch-name>.patch

# Configure and build the kernel
make olddefconfig
make -j"$(nproc)"
```

Installation depends on the target distribution and the selected kernel packaging workflow.

Always retain a known-good kernel and test experimental builds in a controlled environment.

## Project Status

**Work in progress.**

The codebase is expected to evolve as new experiments, kernel modifications, and performance investigations are introduced. Current implementations and their measured effects should be treated as experimental until independently validated.

## Disclaimer

This project modifies low-level operating system and virtualization behavior. Experimental changes may affect system stability, guest compatibility, security mitigations, and timing behavior.

Use experimental builds only in environments where failures can be safely recovered from.
