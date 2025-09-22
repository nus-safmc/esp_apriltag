idf_component_register(
  SRCS 
    take_picture.c 
    apriltag.c 
    tag36h11.c
    common/g2d.c
    common/getopt.c
    common/homography.c
    common/image_u8.c
    common/image_u8_parallel.c
    common/image_u8x3.c
    common/image_u8x4.c
    common/matd.c
    common/pam.c
    common/pjpeg-idct.c
    common/pjpeg.c
    common/pnm.c
    common/postscript_utils.h
    common/pthreads_cross.c
    common/pthreads_cross.h
    common/string_util.c
    common/svd22.c
    common/time_util.c
    common/unionfind.c
    common/workerpool.c
    common/zarray.c
    common/zhash.c
    common/zmaxheap.c
  PRIV_INCLUDE_DIRS . common
  PRIV_REQUIRES nvs_flash esp_psram
)
component_compile_options(-Wno-error)
# component_compile_options(-Wno-error=format= -Wno-format)
