FROM almalinux:9
RUN usedadd expense
# unitl here it will run as root user
USER expense
# from here it will run as expense user thus limiting the permissions
CMD ["sleep", "100"]