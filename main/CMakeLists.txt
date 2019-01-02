set(COMPONENT_SRCS pppos_client_main.c)

set(COMPONENT_EMBED_TXTFILES "server_root_cert.pem")

set(COMPONENT_REQUIRES lwip nvs_flash pppos json)

register_component()
