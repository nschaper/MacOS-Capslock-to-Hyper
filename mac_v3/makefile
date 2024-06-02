compile:
        # @HYPER_KEY sets a temporary env variable, only lasts for the current command
        # envsubst will subtitute the env text for ${HYPER_KEY} in the source file
	@HYPER_KEY=right_shift,right_control,right_option envsubst < capslock.yml > expanded_capslock.yml
	yq eval expanded_capslock.yml -o=json > capslock.json

install: compile
	mkdir -p $$HOME/.config/karabiner/assets/complex_modifications/
	cp capslock.json $$HOME/.config/karabiner/assets/complex_modifications/

all:
	mkdir -p $$HOME/.config/karabiner/
	cp karabiner.json $$HOME/.config/karabiner/

.PHONY: compile,install,all
