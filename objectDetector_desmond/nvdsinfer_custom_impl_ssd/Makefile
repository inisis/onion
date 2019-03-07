###############################################################################
#
# Copyright (c) 2018 NVIDIA CORPORATION.  All Rights Reserved.
#
# NVIDIA CORPORATION and its licensors retain all intellectual property
# and proprietary rights in and to this software, related documentation
# and any modifications thereto.  Any use, reproduction, disclosure or
# distribution of this software and related documentation without an express
# license agreement from NVIDIA CORPORATION is strictly prohibited.
#
###############################################################################

CUDA_VER:=10.0
CC:= g++

CFLAGS:= -Wall -Werror -std=c++11 -shared -fPIC
CFLAGS+= -I../../includes -I/usr/local/cuda-$(CUDA_VER)/include -I/data/TensorRT-5.0.2.6/include

LIBS:= -L/data/TensorRT-5.0.2.6/lib -L/usr/local/cuda-$(CUDA_VER)/lib64 -lnvinfer -lnvparsers -lcudart -lcublas 
LFLAGS:= -Wl,--start-group $(LIBS) -Wl,--end-group

SRCFILES:= nvdsparsebbox_ssd.cpp 
TARGET_LIB:= libnvdsinfer_custom_impl_ssd.so

all: $(TARGET_LIB)

$(TARGET_LIB) : $(SRCFILES)
	$(CC) -o $@ $^ $(CFLAGS) $(LFLAGS)

clean:
	rm -rf $(TARGET_LIB)
