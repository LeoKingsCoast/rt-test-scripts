# RT Test Scripts

These are short scripts meant to evaluate the real-time capabilities of a
Linux system. This was made to be used inside [meta-tests-preempt-rt](https://github.com/LeoKingsCoast/meta-tests-preempt-rt).

## Dependencies

- [rt-tests](https://wiki.linuxfoundation.org/realtime/documentation/howto/tools/rt-tests)

## Running the Scripts

1. Run `run-benchmark` to output a `ciclictest` histogram to an output file:

    ```bash
    run-benchmark data
    ```

    Optional flags:

    - `-q`: Quiet. The command prints nothing to `stdout` while running
    - `-t TIME`: Specify a `TIME` duration for the test. Default value: `10s`. Example values: `30s`, `6h`.

1. Run `gen-hist` to generate a latency histogram of the data from the previous command.

    ```bash
    gen-hist data hist.png
    ```

    For the command to run, the `plot-settings` file must be available. The
    script looks for it in the current directory, inside the HOME directory
    and inside `/etc`, in this order.

