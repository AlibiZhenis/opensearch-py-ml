ARG OPENSEARCH_VERSION
FROM opensearchproject/opensearch:$OPENSEARCH_VERSION

ARG opensearch_path=/usr/share/opensearch
ARG opensearch_yml=$opensearch_path/config/opensearch.yml

ARG SECURE_INTEGRATION
RUN echo "plugins.ml_commons.only_run_on_ml_node: false" >> $opensearch_yml;
RUN echo "plugins.ml_commons.native_memory_threshold: 100" >> $opensearch_yml;
RUN if [ "$SECURE_INTEGRATION" != "true" ] ; then echo "plugins.security.disabled: true" >> $opensearch_yml; fi
