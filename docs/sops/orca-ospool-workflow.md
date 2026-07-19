# ORCA on OSPool (HTCondor)

This is the SOP for running containerized ORCA quantum chemistry
calculations on OSPool via HTCondor.

## Prerequisites

- An active OSPool account (see the [New Member Guide](../new-member-guide.md)
  if you don't have one yet)
- Access to the group's OSPool project/allocation
- An ORCA input file (`.inp`) for the calculation you want to run

## 1. Prepare your input file

1. Write your ORCA `.inp` file locally, specifying the method, basis
   set, and molecule geometry.
2. Validate the input syntax against a known-good example before
   submitting — a bad input wastes queue time.

## 2. Prepare the HTCondor submit file

1. Create a submit description file (`.sub`) that references the
   group's ORCA container image and your `.inp` file.
2. Set `request_cpus`, `request_memory`, and `request_disk` based on
   the size of your calculation.

Example skeleton:

```
universe = vanilla
executable = run_orca.sh
arguments = $(input_file)
should_transfer_files = YES
when_to_transfer_output = ON_EXIT
transfer_input_files = $(input_file)
request_cpus = 4
request_memory = 8GB
request_disk = 4GB
output = job.out
error = job.err
log = job.log
queue
```

## 3. Submit the job

```bash
condor_submit my_job.sub
```

## 4. Monitor the job

```bash
condor_q
```

Check `job.out` / `job.err` for progress once the job starts running.

## 5. Retrieve and check output

1. Confirm the job completed successfully (`condor_q -hist` or check
   `job.log` for a normal termination).
2. Inspect the ORCA output file for convergence / normal termination
   messages before using the results.
3. Move results to the shared Drive if they're large; keep only
   small summary files in your project repo.

## Troubleshooting

- **Job stuck idle**: check `condor_q -analyze <job_id>` for
  matchmaking issues (often a resource request that's too large).
- **ORCA errors on startup**: verify the container image tag is
  current — ask in the group chat if unsure which tag to use.
