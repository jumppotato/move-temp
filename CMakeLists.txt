cmake_minimum_required(VERSION 3.9)
project(jshare_server)

set(CMAKE_CXX_STANDARD 11)

include_directories(../jshare_server
        ./thirdparty
        ./netgo
        ./netgo/include
        ./proto
        )

aux_source_directory(cps_server DIR_SRCS)
aux_source_directory(cps_server/boss DIR_SRCS)
aux_source_directory(cps_server/business DIR_SRCS)
aux_source_directory(cps_server/common DIR_SRCS)
aux_source_directory(cps_server/config DIR_SRCS)
aux_source_directory(cps_server/configor DIR_SRCS)
aux_source_directory(cps_server/const DIR_SRCS)
aux_source_directory(cps_server/db DIR_SRCS)
aux_source_directory(cps_server/exception DIR_SRCS)
aux_source_directory(cps_server/monitor DIR_SRCS)
aux_source_directory(cps_server/const DIR_SRCS)
aux_source_directory(cps_server/request_handler DIR_SRCS)
aux_source_directory(cps_server/service DIR_SRCS)
aux_source_directory(cps_server/utils DIR_SRCS)
aux_source_directory(cps_server/utils/jsf_json DIR_SRCS)
aux_source_directory(cps_server/utils/login DIR_SRCS)

aux_source_directory(netgo DIR_SRCS)
aux_source_directory(proto DIR_SRCS)
aux_source_directory(ut DIR_SRCS)
aux_source_directory(ads_common DIR_SRCS)
aux_source_directory(thirdparty/boost DIR_SRCS)

add_executable(jshare_server
        ${DIR_SRCS}
        cps_server/
        ads_common/
        cps_server/utils
        proto/function_api.pb.h
        proto/business
        proto/skuservice
        netgo/
        netgo/include/
        cps_server/const/
        cps_server/request_handler/
        cps_server/business/
        cps_server/business/url_convert/
        )

