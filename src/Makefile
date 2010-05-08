
ERLC = erlc
EBIN_DIR = ../ebin
ERLC_FLAGS += -I ./src -I ../include +debug_info
ERL_OBJECTS := ${EBIN_DIR}/eldap.beam ${EBIN_DIR}/ELDAPv3.beam ${EBIN_DIR}/eldap_fsm.beam 

.SUFFIXES: .asn1 .erl .beam

$(EBIN_DIR)/%.beam: %.erl
	$(ERLC) $(ERLC_FLAGS) -o $(EBIN_DIR) $<

.PHONY: all
all: asn1 $(ERL_OBJECTS)

.PHONY: asn1
asn1: ELDAPv3.erl ../ebin/ELDAPv3.beam

ELDAPv3.erl: ../asn1/ELDAPv3.asn1
	${ERLC} ../asn1/ELDAPv3.asn1
	mv ELDAPv3.beam ${EBIN_DIR}

.PHONY: clean
clean:
	-rm $(ERL_OBJECTS) ELDAPv3.erl ELDAPv3.asn1db ELDAPv3.hrl


