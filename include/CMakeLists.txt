add_library(learn-open-gl)

target_sources(learn-open-gl
  PRIVATE
    # source go files here
    glad/gl.c
  PUBLIC
    FILE_SET HEADERS
    FILES
      # headers go here
      glad/gl.h
)
