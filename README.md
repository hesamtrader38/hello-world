# hello-world
my first repository
i want to creat new minig pool
@@ -284,9 +284,13 @@ def get_verification_info(self) -> Dict:
                        compiler._get_solc_remappings(config["solc"]["remappings"]),
                    )
                )
                libs = {lib.strip("_") for lib in re.findall("_{1,}[^_]*_{1,}", self.bytecode)}
                compiler_settings = {
                    "evmVersion": self._build["compiler"]["evm_version"],
                    "optimizer": config["solc"]["optimizer"],
                    "libraries": {
                        Path(source_fp).name: {lib: self._project[lib][-1].address for lib in libs}
                    },
                }
                self._flattener = Flattener(source_fp, self._name, remaps, compiler_settings)
