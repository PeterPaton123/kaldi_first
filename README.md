# This repo exists entirely in the egs directory of kaldi on my local machine, the audio data was taken from a similar directory.

# I'm following the instructions detailed here in the Kaldi documentation https://kaldi-asr.org/doc/kaldi_for_dummies.html
# The audio for training/testing is in digits_audio and the relevant data detailing them is in data/ test and train

# I have installed SRILM as instructed and this is the error I am reaching in running ./run.sh

===== MONO TRAINING =====

steps/train_mono.sh --nj 1 --cmd run.pl data/train data/lang exp/mono
steps/train_mono.sh: Initializing monophone system.
feat-to-dim 'ark,s,cs:apply-cmvn --utt2spk=ark:data/train/split1/1/utt2spk scp:data/train/split1/1/cmvn.scp scp:data/train/split1/1/feats.scp ark:- | add-deltas ark:- ark:- |' - 
apply-cmvn --utt2spk=ark:data/train/split1/1/utt2spk scp:data/train/split1/1/cmvn.scp scp:data/train/split1/1/feats.scp ark:- 
WARNING (apply-cmvn[5.5.846~1-a7c42]:Open():util/kaldi-table-inl.h:106) Failed to open script file data/train/split1/1/feats.scp
ERROR (apply-cmvn[5.5.846~1-a7c42]:SequentialTableReader():util/kaldi-table-inl.h:860) Error constructing TableReader: rspecifier is scp:data/train/split1/1/feats.scp

[ Stack-Trace: ]
/home/peter/Documents/kaldi/src/lib/libkaldi-base.so(kaldi::MessageLogger::LogMessage() const+0x793) [0x7f433416a183]
apply-cmvn(kaldi::MessageLogger::LogAndThrow::operator=(kaldi::MessageLogger const&)+0x25) [0x55cb809051c1]
apply-cmvn(kaldi::SequentialTableReader<kaldi::KaldiObjectHolder<kaldi::Matrix<float> > >::SequentialTableReader(std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> > const&)+0xc4) [0x55cb809147fe]
apply-cmvn(main+0x7b7) [0x55cb80903720]
/lib/x86_64-linux-gnu/libc.so.6(__libc_start_main+0xf3) [0x7f4333d630b3]
apply-cmvn(_start+0x2e) [0x55cb80902eae]

kaldi::KaldiFatalErroradd-deltas ark:- ark:- 
ERROR (feat-to-dim[5.5.846~1-a7c42]:main():feat-to-dim.cc:58) Could not read any features (empty archive?)

[ Stack-Trace: ]
/home/peter/Documents/kaldi/src/lib/libkaldi-base.so(kaldi::MessageLogger::LogMessage() const+0x793) [0x7fef3f4d5183]
feat-to-dim(kaldi::MessageLogger::LogAndThrow::operator=(kaldi::MessageLogger const&)+0x25) [0x55e7a7d075d9]
feat-to-dim(main+0x2f7) [0x55e7a7d06f20]
/lib/x86_64-linux-gnu/libc.so.6(__libc_start_main+0xf3) [0x7fef3f0ce0b3]
feat-to-dim(_start+0x2e) [0x55e7a7d06b6e]

kaldi::KaldiFatalErrorerror getting feature dimension


