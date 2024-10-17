ARG version
FROM almalinux:${version:-9}
# variables used in ARG as 1st instruction before FROM does not work after FROM
ARG course="docker" \
    duration="120hrs"
ENV course="DevOps with AWS" \
    duration=$duration
RUN echo "Course=$course, duration=$duration, version=$version"
CMD ["sleep", "100"]