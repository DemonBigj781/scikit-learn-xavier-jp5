scikit-learn - Xavier JP5
========================

This fork provides the machine-learning utility dependency required by the Xavier worker environment. It also carries the native AArch64 build needed to avoid the static TLS failure caused by an incompatible bundled OpenMP runtime.

Xavier-specific constraint
--------------------------

The validated wheel uses the system ``libgomp`` instead of a conflicting bundled copy. This is a packaging correction for JetPack 5, not a broad runtime preload workaround.

Role in the Xavier stack
------------------------

* Aligns with the pinned NumPy and SciPy versions.
* Builds natively for Python 3.10 on AArch64.
* Prevents the ``cannot allocate memory in static TLS block`` import failure.
* Supports Horde safety and model-analysis dependencies.

Project status
--------------

This is an experimental integration fork. Package success does not prove end-to-end Worker v13 operation.

Build discipline
----------------

Native builds must use exactly one compiler worker.

Upstream
--------

Forked from ``scikit-learn/scikit-learn``. Upstream remains authoritative for general scikit-learn development.
