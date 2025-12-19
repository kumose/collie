#
# Copyright 2024 Kumo.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
###########################################################################
# below are examples, after initialization, modify it to your own.
###########################################################################
###kmcmake_example


file(GLOB_RECURSE TSL_HDRS "tsl/*.h")
kmcmake_cc_interface(
        NAMESPACE ${PROJECT_NAME}
        NAME tsl
        HEADERS
        ${TSL_HDRS}
        CXXOPTS
        ${KMCMAKE_CXX_OPTIONS}
        PUBLIC
)

file(GLOB_RECURSE TSL_HDRS "pmap/*.h")
kmcmake_cc_interface(
        NAMESPACE ${PROJECT_NAME}
        NAME pmap
        HEADERS
        ${TSL_HDRS}
        CXXOPTS
        ${KMCMAKE_CXX_OPTIONS}
        PUBLIC
)

