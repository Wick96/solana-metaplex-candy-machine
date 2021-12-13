setup-solana:
	@echo "Configure solana to https://api.devnet.solana.com..."
	@echo ""
	@solana config set --url https://api.devnet.solana.com
	@echo ""
	@echo ""
	@[ -f '/home/solana/config/solana_devnet.json' ] && echo Config keypair already exists! Skip generation... || echo Generation solana keypair...
	@echo ""
	@[ ! -f '/home/solana/config/solana_devnet.json' ] && solana-keygen new --outfile /home/solana/config/solana_devnet.json || true
	@echo ""
	@echo ""
	@echo "Set default config to /home/solana/config/solana_devnet.json"
	@echo ""
	@solana config set --keypair /home/solana/config/solana_devnet.json

setup-metaplex:
	@[ -d '/home/solana/metaplex' ] && echo Metaplex already cloned! Skiping... || echo Cloning metaplex...
	@echo ""
	@[ ! -d '/home/solana/metaplex' ] && git clone https://github.com/metaplex-foundation/metaplex.git || true
	@echo ""
	@echo ""
	@echo "Installing and building metaplex...."
	@echo ""
	@cd /home/solana/metaplex/js && yarn install && yarn bootstrap && yarn build
