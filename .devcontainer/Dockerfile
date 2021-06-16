FROM pandoc/latex:2.14.0.2

RUN apk --no-cache add make

# Install Microsoft True Type Fonts
RUN apk --no-cache add msttcorefonts-installer fontconfig && \
    update-ms-fonts && \
    fc-cache -f
    
ENTRYPOINT tail -f /dev/null
CMD [ "/bin/bash" ]
