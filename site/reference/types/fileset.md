# type: fileset

The &lt;fileset&gt; objects represent the set of files required for installing a software package.

# description of &lt;fileset&gt;

Returns a description of a set of installation files.

# lpp_name of &lt;fileset&gt;

Licensed Program Product(s) of the fileset.Example: (lpp_name of it &amp; &quot; ver = &quot; &amp; version of it as string) of filesets matching &quot;lpp_name = &#39;bos.terminfo.rte&#39;&quot; of object repository - Returns a formatted list of filesets with the specified Licensed Program Product name.

# product of &lt;fileset&gt;

Returns the product corresponding to the specified fileset.

# root part of &lt;fileset&gt;

Returns the machine-specific portions of the specified fileset (the root part), which contains the part of the product that cannot be shared among machines -- each client must have its own copy. For a standard system, files in the root part are stored in the root (/) file tree.

# share part of &lt;fileset&gt;

Returns the share part of the specified fileset.

# update of &lt;fileset&gt;

Returns the update number for the specified fileset.Example: updates of filesets matching &quot;lpp_name = &#39;bos.terminfo.rte&#39;&quot; of object repository - Returns the update numbers of the specified filesets.

# usr part of &lt;fileset&gt;

Returns the machine-shareable portions of the specified fileset (the usr part), which contains the part of the product that can be shared among several machines with compatible hardware architectures. The usr part of the fileset contains files that reside in the /usr or /opt file system.

# version of &lt;fileset&gt;

Returns the version of the specified fileset.

# version record of &lt;fileset&gt;

Returns the version record corresponding to the specified fileset as a fileset version record.

# &lt;fileset&gt; as string

Casts a fileset as a string type.