#
# Copyright 2024 The Kumo Authors.
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

find_package(GTest REQUIRED)

set(TEST_CASES
        container_memory_test
        hash_policy_testing_test
        node_hash_policy_test
        raw_hash_set_test
        raw_hash_set_allocator_test
        flat_hash_set_test
        flat_hash_map_test
        node_hash_map_test
        node_hash_set_test
        parallel_flat_hash_map_test
        parallel_flat_hash_set_test
        parallel_node_hash_map_test
        parallel_node_hash_set_test
        parallel_flat_hash_map_mutex_test
        dump_load_test
        erase_if_test
        btree_test
)
foreach (tn ${TEST_CASES})
    kmcmake_cc_test(
            NAME ${tn}
            MODULE pmap
            SOURCES
            ${tn}.cc
            DEFINES
            "-DUNORDERED_SET_CXX17"
            CXXOPTS
            ${KMCAMKE_CXX_OPTIONS}
            LINKS

            GTest::gtest
            GTest::gmock
            GTest::gtest_main
            ${KMCMAKE_DEPS_LINK}
    )
endforeach ()